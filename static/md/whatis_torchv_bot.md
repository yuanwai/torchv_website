## TorchV Bot介绍

TorchV Bot是一款基于大语言模型（Large Language Model，后文简称*LLM*）和检索增强生成（Retrieval-augmented generation，后文简称*RAG*）技术的人工智能问答机器人，属于TorchV最主要的三款产品（Bot、Assistant和Analyst）中一款。

在使用方面，TorchV Bot的产品价值最简单总结就是：**将您业务中已有的各类文档扔进去，就可以快速形成知识库和问答系统，可以作为对外的客服机器人使用，也可以作为对内的业务助理使用**。

TorchV Bot是基于TorchV RAG中间件系统的应用，从整体系统架构来看，具体如下：

![image-20240125093416786](/images/docs/manual/torchvbot_arc.png)

在整套架构中，本文提到的TorchV Bot仅仅属于产品层的其中一个产品，下面我们从下往上逐层描述：

-  **大语言模型（LLMs，后面统称LLMs或LLM）**：默认采用在线大模型（API调用）或本地LLMs，**因为OpenAI的ChatGPT、Anthropic的Claude等存在政策风险，所以本产品在面向国内市场客户时一律采用国产LLMs**，常见的LLMs为通义千问（QWen-72B/14B）、百川（Baichuan2-13B/52B）、智谱（ChatGLM3-6B/ChatGLM-Turbo/ChatGLM4）和月之暗面（Moonshot-v1-32K/128K）等，另外也会在特定业务是采用Deep-Seek、InterLM等偏专业能力的大语言模型。如需进行本地化部署，则尽量选取参数量更少的模型，或采用类似MoE形式的多个LLMs混搭。
-  **中间件层**：包括TorchV RAG和其他中间件，在下文会具体描述其作用。中间件层是为了更好地帮助应用使用LLMs的能力，如减少幻觉、提高时效性、数据安全等，也包括更好的交互方式，更经济的推理成本等；
-  **基线产品**：TorchV Bot属于现有的三款基线产品之一，具备完整的功能，可直接用于诸多应用场景。本文所提及的试用平台就是属于TorchV Bot的Beta 1版本，业务无关，是一个通用产品。关于TorchV Bot的具体介绍和操作说明，下文会介绍；
-  **业务应用**：基于TorchV Bot产品基线，可以结合不同业务类型和场景开发多种具体应用，如加上**名片应用**之后形成的“*产业招商数字名片*”应用；加上**工业操作和检修标准手册知识**之后可以解决工业产业人员的日常工作知识咨询，成为*工业专家机器人*。应用场景业态丰富，目前TorchV已经有落地案例或正在开展合作的行业类型已达9类。



TorchV Bot是基于LLM和RAG的，为了方便更多朋友进一步了解，这里再介绍一下RAG，如果您对RAG已经了解，可以直接跳过该章节。



## RAG

RAG（Retrieval-Augmented Generation，检索增强生成）是为大语言模型 (LLMs) 提供了从数据源检索的信息，以此为基础生成回答。简而言之，RAG 结合了搜索技术和大语言模型的提示功能，即模型根据搜索算法找到的信息作为上下文来回答查询问题。无论是查询还是检索的上下文，都会被整合到发给大语言模型的提示中，然后让大语言模型根据召回的事实内容进行润色输出。

在2023 年，大语言模型逐渐火热之后，基于 RAG 架构的大语言模型系统成为最受欢迎的技术。许多产品几乎全依赖 RAG 架构，这包括结合网络搜索引擎和大语言模型的问答服务，以及数以百计的数据交互应用程序。



### **RAG的优势**

RAG结合大语言模型使用，可以有效解决大语言模型本身存在的三个主要问题：

- **数据时效性问题**：RAG可以根据用户上传的最新知识，将系统的知识时效性快速提升，而传统LLMs则需要进行成本高昂的大模型全(或增)量训练或微调；
- **幻觉问题**：LLMs对于用户行业知识匮乏的时候，会出现常见的幻觉问题。使用RAG可以基于给定内容进行检索，降低最终输出的幻觉。TorchV Bot提供系统级参数控制，甚至可以设置在检索召回内容质量不高的情况下，不让LLMs介入，而是直接回复“不知道”；
- **数据安全问题**：对于数据安全要求极高的企业用户，如果不想使用在线大语言模型（如ChatGPT、通义千问、文心一言等），那么可以采用完全本地化部署。采用RAG可极大降低LLMs要求，配合百亿级别参数的可本地部署大模型即可提供绝大多数AI服务，还让企业数据保不出内网。

#### **RAG简要介绍**

关于RAG的简要介绍，特别是技术实现，可以参看*附录1*.

## 其他中间件

除了RAG，架构中还是用了多个中间件，如幂等分类器（IC）、执行器（Actuator）和连接器（Connector），下面简要叙述它们的作用：

- **幂等分类器（IC）**：IC的作用是理解用户输入内容，将输入内容中的实体内容（entity）、时间段和意图（特别涉及到行业分类、多学科分类等）进行识别，提前做路由判断，帮助检索系统找到更准确的内容。帮助RAG系统过滤掉绝大部分信息，加入更准确的辅助信息，帮助RAG系统过滤干扰内容，帮助LLMs减少幻觉。TorchV IC尚属于开发的早期，还有不少工作需要继续迭代；
- **执行器（Actuator）**：根据LLMs生成的代码，特别是CSS等，会出现随机现象。执行器在执行过程中会加入全局样式，保证输出风格尽量统一；
- **连接器（Connector）**：只需将文件目录、数据库链接、内部API等配置完成，即可让本地数据在使用时完成数据格式转换和数据抽取，实现数据格式统一，且可在后台提供清晰UI界面，让用户具备自行管理内部数据绑定的能力。



## **有哪些可以值得说道的特性？**

![image-20240125101914401](/images/docs/manual/6features.png)



### 1.开箱即用

TorchV Bot第一个特点是开箱即用，这里其实有两层意思：

- **开户即用**：开通TorchV Bot账号，即可开始使用。LLM+RAG整套架构的技术环节非常多，其中也不乏难点，行业内大部分研发人员都有一种感触就是“入门简单，精通很难”，真正要实现生产级别的使用，不是搭一个RAG框架就能解决的，尤其是像我们这样采用国产LLM的就更少了。使用TorchV Bot，用户无需关心技术、优化迭代和服务器等问题；
- **无需维护**：阻碍传统的NLP机器人有效使用的最大问题就是知识库维护，工作人员需要先理解内容，再抽取问答对（或FAQ），然后入库测试。然后更大的工作量也将到来，就是相似问法的匹配。比如您已经维护了“哪里有厕所？”这个问题和答案，那么用户如果提问“哪里有WC？”，“哪里有洗手间？”，甚至有人问“茅坑在哪里？”，那就无法理解和回答了。这时候就需要去维护相似问法，过程非常繁琐，即使维护了行业意图包。而基于LLM+RAG的TorchV Bot的理解能力会非常强，BM25（可以理解为关键词检索）+语义检索（相近含义的检索）+LLM的回复，会让Bot（机器人）的理解能力至少达到普通人类的水平。

具备开通即可使用的便捷，以及拥有无需维护就能达到生产应用级别的能力，注定会让TorchV Bot适合于越来越多的行业应用场景。



### 2. 访问权限控制

对于企业应用，即使是内部使用，一些敏感文件内容依然需要保密，如销售报表，最好只能让总经理、销售本人和财务人员看到。如果直接放在LLM中，那么实习生也能对“我要看一下XX部门今年的销售数据”等问题进行提问，并获得答案。而采用TorchV Bot则可以通过建立受保护的文件夹来有效设置访问权限，当然该特性目前仅在企业版中提供。



### 3. 高精确度

这其实是基本条件，TorchV Bot在这些方面已经获得现有客户的认可。

我们没有做任何标准评测，而且以后应该也不会去参加各种评测。因为我们发现，在我们前面接触的行业客户中，他们的提问我们都很难看懂，更加无法理解输出的答案是否优秀。目前的反馈都是基于约9个类型行业的真实客户使用反馈，客户试用之后的签约是最好的证明，特别是通过PLG来的客户。



### 4. 支持全量私有化

针对数据敏感的服务，如涉及到企业经营数据、合同、工艺流程等知识内容，都会有全量私有化部署的需求，既可以断开外网在企业内部使用。TorchV Bot支持全量部署，包括国产大语言模型（会配合客户申请Model的商用授权），全套RAG架构，以及应用。



### 2.5 轻松扩展“+AI”

TorchV Bot从标准版开始就支持API开放，客户可以使用API与自己的原有业务对接，包括小程序、HTML、APP、大屏数字人和具身机器人等。我们也正在开发一键嵌入，估计马上就可以实现让客户使用极少的几行代码将TorchV Bot应用嵌入集成到原系统中。



### 2.6 配置灵活

我们的系统后台配备有各类参数调整的界面，可以让管理人员简便调整参数。如在专业性较强的应用场景，可以将alpha参数偏向于BM25；而在通用场景下，让KNN的权重更大。另外对于大家关心的大模型幻觉问题，我们可以设置让系统如何回答——当召回得分的最大分数低于设定的阈值的时候，选择让LLM兜底回答，还是回复“据已有知识，暂时无法回答您的问题！”



