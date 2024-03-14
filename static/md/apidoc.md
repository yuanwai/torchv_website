# 1. 概述

## 1.1 编写目的

TorchV产品在目前的版本迭代中，已经形成了一部分稳定的标准化的文档，针对TorchV应用中的场景，将接口文档固化进行迭代发布更新，服务对接使用TorchV产品的技术&客户进行使用。

## 1.2 读者对象

购买&使用TorchV系列产品的相关技术、产品、客户人员。

## 1.3 文档说明

本文档主要从萌嘉科技的TorchV系列产品的应用场景出发，涵盖后续所有开放的RESTFul API接口文档内容

TorchV Bot所有开放的API接口都需要开发者添加鉴权Header，否则会被拒绝访问，api 有两种接口形式，分别是同步接口和流式接口，通过请求参数来区分

备注：

- 演示环境，URI:`https://demo.torchv.com/openapi`
- 正式环境，URI: `https://api.torchv.com/openapi`

## 1.4 版本记录

| 版本号 | 作者                         | 日期       | 说明                                                    |
| ------ | ---------------------------- | ---------- | ------------------------------------------------------- |
| v0.1   | 肖玉民(xiaoymin@foxmail.com) | 2024/01/27 | 开放接口上线发布，v1版本接口文档梳理完成                |
| v0.2   | 肖玉民(xiaoymin@foxmail.com) | 2024/02/23 | 上线支持通义千问1.5-72B模型，问答Chat接口增加知识库参数 |

# 2. 接口文档

## 2.1 问答completions

### 请求接口

请求接口：/api/v1/chat/completions

接口类型：POST

### 请求Header

| 参数名称      | 类型   | 必填 | 描述                                                         |
| ------------- | ------ | ---- | ------------------------------------------------------------ |
| Content-Type  | string | 是   | 请求的数据格式，目前仅支持 JSON 格式，固定填写"application/json" |
| Authorization | string | 是   | 请求鉴权的 APIKey，由TorchV提供。Bearer 开头，例如：Bearer sk-xxxx |

### 输入Body

统一输入参数如下：

```JSON
{
    //会话id，一个会话中，服务端会自动包含上下文语义信息，如果没有id，那么服务端会生成一个新的
    "conversationId":"6A204BD89F3C8348AFD5C77C717A097A",
    // 模型编码，TorchV bot平台对接的支持的模型编码，参考附录3.2
    "model":"glm-3-turbo",
    // 知识库Id，在平台的：知识库 功能列表可以查看，该参数可为空
    "containerId":["1751484246895214593","1751484246895214595"]
    // 是否开启知识库rag检索，默认为true，如果不使用rag检索，则纯使用llm来进行回答
    "rag_search":true,
    // 提问问题，和messages字段互斥，prompt字段不为空的情况下，优先使用该字段
    // prompt字段不为空，并且multipleDialog=true，那么系统会在rag过程中自动开启检索&多轮会话，如果multipleDialog=false，那么不会进行多轮
    "prompt":"请介绍一下杭州西湖?",
    // 消息历史，该字段和prompt互斥，两者不能同时为空，几种情况：
    // 2.如果prompt为空，那么会使用messages字段，此时multipleDialog字段默认为true
    // 3.messages的内容必须是数组，并且必须是user、assistant这样成对出现
    // 4.如果prompt字段和messages字段都不为空，会以prompt进行查询使用
    "messages":[
        {"role": "user", "content": "你好"},
        {"role": "assistant", "content": "你好,请问有什么可帮您"}
    ],
    // 是否流式SSE请求,false的情况，响应内容为application/json
    "stream":true,
    // 是否开启多轮对话，默认true，如果开启该参数，必须保证conversationId一致，服务端会自动多轮会话，否则每次只试用prompt参数进行检索请求
    "multipleDialog":true,
    // 采样温度，控制输出的随机性，必须为正数取值范围是：(0.0,1.0]，不能等于 0，默认值为 0.95
    "temperature":0.95,
    // 用温度取样的另一种方法，称为核取样取值范围是：(0.0, 1.0) 开区间，不能等于 0 或 1，默认值为 0.7模型考虑具有 top_p 概率质量tokens的结果
    // 例如：0.1 意味着模型解码器只考虑从前 10% 的概率的候选集中取tokens
    // 建议您根据应用场景调整 top_p 或 temperature 参数，但不要同时调整两个参数
    "top_p":0.7
}
```

| 参数名称       | 类型         | 必填 | 说明                                                         |
| -------------- | ------------ | ---- | ------------------------------------------------------------ |
| conversationId | string       | N    | 会话id，一个会话中，服务端会自动包含上下文语义信息，如果没有id，那么服务端会生成一个新的 |
| containerId    | List<String> | N    | 知识库Id集合，最多支持10个，该参数不为空的情况下，则会根据该条件进行过滤。知识库Id可在平台功能 “知识库”中查看获取 |
| rag_search     | bool         | Y    | 是否开启知识库rag检索，默认为true，如果不使用rag检索，则纯使用llm来进行回答 |
| multipleDialog | bool         | Y    | 是否开启多轮对话，默认true，如果开启该参数，必须保证conversationId一致，服务端会自动多轮会话，否则每次只试用prompt参数进行检索请求 |
| prompt         | string       | Y    | 提问问题，该字段和messages字段二选一                         |
| messages       | List<Object> | N    | 消息历史，该字段和`prompt`字段互斥，如果`prompt`为空，那么会使用messages字段，同时`multipleDialog`字段会默认开启。在TorchV Bot的RAG架构体系中，如果客户端只传递prompt字段，那么系统会自动保留会话历史，进行多轮对话。 |
| -   role       | string       | Y    | 角色，目前两种，user、assistant                              |
| -   content    | string       | Y    | 内容                                                         |
| stream         | bool         | Y    | 是否流式请求，默认True                                       |
| model          | string       | N    | TorchV Bot对接支持的模型编码，为空的情况下则由系统默认指定，支持的模型包括：glm-3-turbo、glm-4、Baichuan2-Turbo、Baichuan2-Turbo-192k、qwen-72b-chat等 |
| temperature    | float        | N    | 采样温度，控制输出的随机性，必须为正数取值范围是：(0.0,1.0]，不能等于 0，默认值为 0.95 |
| top_p          | float        | N    | 用温度取样的另一种方法，称为核取样取值范围是：(0.0, 1.0) 开区间，不能等于 0 或 1，默认值为 0.7模型考虑具有 top_p 概率质量tokens的结果 |

### 输出参数

按OpenAI的格式进行输出，并且会返回TorchV平台对引用知识库等相关信息

```JSON
{
    // 创建时间
    "created":1705392413186,
    // 当前请求id
    "id":"6A204BD89F3C8348AFD5C77C717A097A",
    // 当前会话id
    "conversationId":"d037a9a9c2a347d0996bd70bbba1ee82",
    // 模型
    "model":"glm-3-turbo",
    // 消耗总时间,单位毫秒
    "costTime":0,
    // token消耗情况
    "usage":{
        // 回答内容消耗token数
        "completion_tokens": 17,
        // prompt请求消耗token数量
        "prompt_tokens": 20,
        // 总共消耗token数量
        "total_tokens": 37
    },
    // 响应的消息内容
    "choices":[{
       // 下标
      "index":0,
      // 完成标志，正在生成时为null，生成结束为stop，异常情况则为error
      "finish_reason":"stop",
      // 响应消息
      "message":{
           // 角色，user-用户，assistant-大模型助理回答 
           "role":"assistant",
           // 内容，不同的角色类别，有不同的内容
           "content":"西湖.."
      }
    }],
    // 多媒体信息
    "multiParts":[
        { 
            // 数据集名称
            "dataSetName":"./杭州最新景区介绍.pdf"
            // 所属页码
            "page":12,
            // 类别，image-图片，video-视频，mp3-音频
            "category":"image",
            // 值信息
            "value":"http://www.torchv.com/1.png"
        }
    ],
    // 引用段落信息
    "paragraphs":[
        {
            // 知识库code
            "containerId":"" ,
            // 知识库名称
            "containerName":""
            // 数据集id
            "dataId":"",
            // 数据集名称
            "dataSetName":"",
            // 所属页码
            "page":12,
            // 原文内容
            "content":"西湖位于杭州......"
        }
    ]，
    // 引用来源主题信息
    "references":[
        {
        // 知识库code
        "containerId":"" ,
        // 知识库名称
        "containerName":""
        // 数据集id
        "dataId":"",
        // 数据集名称
        "dataSetName":"",
        // 数据集的url地址
        "dataSetUrl":"http://xxx.com/1.pdf"
        // 数据集后缀类型，eg：pdf、docx、txt等等
        "suffix":"pdf"
        }
    ]

}
```

⚠️注意：在流式SSE接口和同步接口的情况下，输出会有不同的差别

### SSE流式接口

SSE接口区分不同的情况：

- 在正在生成响应消息过程中，字段：usage、paragraphs、multiParts、references不会返回，只有在流式结束的状态下才全部返回。
- 当设置encode字段为true时，需要对sse协议的data字段进行base64解码，解码后的结构会同响应的JSON内容保持一致。

如下：

```SQL
data:{"created":1706889256592,"id":"1753446746939256834","model":"glm-3-turbo","costTime":2019,"conversationId":"1753446746939256832","references":[],"paragraphs":[],"multiParts":[],"choices":[{"message":{"role":"assistant","content":"门"}}]}
id:rag-torch-vector-llm-1753446755407556608
event:add

//more....

data:{"created":1706889256592,"id":"1753446746939256834","model":"glm-3-turbo","costTime":6173,"conversationId":"1753446746939256832","usage":{"completion_tokens":163,"prompt_tokens":873,"total_tokens":1036},"references":[{"containerId":"1748606692450410496","containerPkId":"34","containerName":"EP15RAG讨论会","dataSetId":"1750024858590302208","dataSetUrl":"https://chat2kl.oss-cn-beijing.aliyuncs.com/1706909030917734400/2024/0124/aa829ad5-53ef-49ac-84c8-1961d9018075.pdf?OSSAccessKeyId\u003dLTAI5t6CsmJ2DSBfqFAnjYv5\u0026Expires\u003d2021433412\u0026Signature\u003dP16QxcpthkLrZXSnlGbOtXVRk%2BA%3D","dataSetPkId":"97","dataSetName":"医保异地就医现金报销省外受理业务.pdf","suffix":"pdf"}],"paragraphs":[{"containerId":"1748606692450410496","containerPkId":"34","containerName":"EP15RAG讨论会","dataSetId":"1750024858590302208","dataSetPkId":"97","dataSetName":"医保异地就医现金报销省外受理业务.pdf","page":1,"content":"医保异地就医现⾦报销省外受理业务\n截⾄2022年1⽉31⽇，异地报销受理业务已经开展四年多时间，省外⽹点已成功受理并办结\n了21790⼈次报销资料。四年多时间，就有21790⼈次异地就医⼈员不⽤跑回深圳来，直接在\n当地提交资料就可以申请报销，减少来回奔波之苦。\n办事指南\n受理对象及内容\n异地报销受理业务是为我市参保⼈异地就医发⽣的⻔诊和住院基本医疗费⽤、地⽅补充医疗\n费⽤，提供异地收取报销材料服务。业务受理对象及内容具体如下：\n1、住院医疗费⽤报销\n参保状态正常的我市基本医疗保险⼀档、⼆档（少⼉）、三档参保⼈,异地就医发⽣的住院基\n本医疗费⽤、地⽅补充医疗费⽤，包括⾃⾏就医、转诊、常住内地登记等住院类型。\n2、⻔诊医疗费⽤报销\n包括普通⻔诊报销、⻔诊年度超⽀、⻔诊特检报销、⻔诊⼤病报销等类型。\n（1）⻔诊普通报销：基本医疗保险⼀档参保⼈，个⼈账户有余额参保⼈。\n（2）⻔诊年度超⽀：基本医疗保险⼀档参保⼈，就诊前连续参保满12个⽉，满⾜办理\n常住内地备案或市外转诊其中⼀种情形。\n（3）⻔诊特检报销：基本医疗保险⼀档参保⼈，满⾜办理常住内地备案或市外转诊其","suffix":"pdf"}],"multiParts":[],"choices":[{"finish_reason":"stop","message":{"role":"assistant","content":""}}]}
id:rag-torch-vector-llm-1753446772830695424
event:add
```

### 同步接口

同步接口则响应完整的JSON内容。如下：

```SQL
{
  "created": 1706889205020,
  "id": "1753446530630610944",
  "model": "glm-3-turbo",
  "costTime": 6429,
  "conversationId": "1753446530626416640",
  "usage": {
    "completion_tokens": 168,
    "prompt_tokens": 873,
    "total_tokens": 1041
  },
  "references": [
    {
      "containerId": "1748606692450410496",
      "containerPkId": "34",
      "containerName": "EP15RAG讨论会",
      "dataSetId": "1750024858590302208",
      "dataSetUrl": "https://chat2kl.oss-cn-beijing.aliyuncs.com/1706909030917734400/2024/0124/aa829ad5-53ef-49ac-84c8-1961d9018075.pdf?OSSAccessKeyId=LTAI5t6CsmJ2DSBfqFAnjYv5&Expires=2021433412&Signature=P16QxcpthkLrZXSnlGbOtXVRk%2BA%3D",
      "dataSetPkId": "97",
      "dataSetName": "医保异地就医现金报销省外受理业务.pdf",
      "suffix": "pdf"
    }
  ],
  "paragraphs": [
    {
      "containerId": "1748606692450410496",
      "containerPkId": "34",
      "containerName": "EP15RAG讨论会",
      "dataSetId": "1750024858590302208",
      "dataSetPkId": "97",
      "dataSetName": "医保异地就医现金报销省外受理业务.pdf",
      "page": 1,
      "content": "医保异地就医现⾦报销省外受理业务\n截⾄2022年1⽉31⽇，异地报销受理业务已经开展四年多时间，省外⽹点已成功受理并办结\n了21790⼈次报销资料。四年多时间，就有21790⼈次异地就医⼈员不⽤跑回深圳来，直接在\n当地提交资料就可以申请报销，减少来回奔波之苦。\n办事指南\n受理对象及内容\n异地报销受理业务是为我市参保⼈异地就医发⽣的⻔诊和住院基本医疗费⽤、地⽅补充医疗\n费⽤，提供异地收取报销材料服务。业务受理对象及内容具体如下：\n1、住院医疗费⽤报销\n参保状态正常的我市基本医疗保险⼀档、⼆档（少⼉）、三档参保⼈,异地就医发⽣的住院基\n本医疗费⽤、地⽅补充医疗费⽤，包括⾃⾏就医、转诊、常住内地登记等住院类型。\n2、⻔诊医疗费⽤报销\n包括普通⻔诊报销、⻔诊年度超⽀、⻔诊特检报销、⻔诊⼤病报销等类型。\n（1）⻔诊普通报销：基本医疗保险⼀档参保⼈，个⼈账户有余额参保⼈。\n（2）⻔诊年度超⽀：基本医疗保险⼀档参保⼈，就诊前连续参保满12个⽉，满⾜办理\n常住内地备案或市外转诊其中⼀种情形。\n（3）⻔诊特检报销：基本医疗保险⼀档参保⼈，满⾜办理常住内地备案或市外转诊其",
      "suffix": "pdf",
      "dataSetUrl": "https://chat2kl.oss-cn-beijing.aliyuncs.com/1706909030917734400/2024/0124/aa829ad5-53ef-49ac-84c8-1961d9018075.pdf?OSSAccessKeyId=LTAI5t6CsmJ2DSBfqFAnjYv5&Expires=2021433412&Signature=P16QxcpthkLrZXSnlGbOtXVRk%2BA%3D"
    }
  ],
  "multiParts": [],
  "choices": [
    {
      "index": null,
      "finish_reason": null,
      "message": {
        "role": "assistant",
        "content": "门诊医疗费用报销包括以下几种类型：\n\n1. **门诊普通报销**：适用于基本医疗保险一档参保人，且个人账户有余额的参保人。\n\n2. **门诊年度超支**：适用于基本医疗保险一档参保人，在就诊前连续参保满12个月，并满足办理常住内地备案或市外转诊其中一种情形。\n\n3. **门诊特检报销**：适用于基本医疗保险一档参保人，满足办理常住内地备案或市外转诊的情形。\n\n4. **门诊大病报销**：这是另一种门诊医疗费用报销的类型。\n\n以上是根据您提供的信息整理的门诊医疗费用报销的种类。如果您需要更详细的信息或有其他问题，请随时提问。"
      }
    }
  ]
}
```

# 3. 附录信息表

## 3.1 接口错误编码

接口响应以HTTP 标准状态码进行响应，具体如下：

> 当接口响应错误异常码时，Status字段会以JSON的内容进行响应,例如：

```JSON
{
  "code": 401,
  "message": "AccessDenied",
  "data": null
}
```

错误编码明细如下表所示

| HTTP 状态码 | 状态(Status)               | (错误)原因                                                   |
| ----------- | -------------------------- | ------------------------------------------------------------ |
| 200         | SUCCESS                    | -                                                            |
| 401         | AccessDenied               | 请求中的 ApiKey 错误，鉴权失败                               |
| 400         | InvalidParameter           | 请求参数非法，格式不符合要求                                 |
| 413         | RequestTooLarge            | 接入层网关返回请求体过大错误，错误如果是由mse网关层直接拦截，则没有 code，并且 message 不能自定义。如果是restful网关拦截返回code。 |
| 429         | RateQuotaLimit             | 触发平台限流措施                                             |
| 429         | InsufficientAccountBalance | 账户余额不足                                                 |
| 500         | InternalError              | 服务器内部异常                                               |

## 3.2 平台支持的大模型编码

Chat接口支持的大模型编码如下表：

| 厂商&品牌 | 模型编码             | 说明 |      |      |      |
| --------- | -------------------- | ---- | ---- | ---- | ---- |
| 智谱AI    | glm-3-turbo          |      |      |      |      |
|           | glm-4                |      |      |      |      |
| 百川智能  | Baichuan2-Turbo      |      |      |      |      |
|           | Baichuan2-Turbo-192k |      |      |      |      |
| 通义千问  | qwen-72b-chat        |      |      |      |      |
|           | qwen1.5-72b-chat     |      |      |      |      |
| 月之暗面  | Moonshot-v1-32k      |      |      |      |      |
|           | Moonshot-v1-128k     |      |      |      |      |