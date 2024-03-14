<script lang="ts">
    import { Section, PricingHead, PricingCard, PricingBodyHead, PricingItemWrapper, FaqItem, Faq } from "flowbite-svelte-blocks";
    import { Button, Modal } from "flowbite-svelte";
    import { CheckCircleSolid} from "flowbite-svelte-icons";
    import Header from '$lib/Header.svelte';
    import Footer from '$lib/Footer.svelte';
    let defaultModal = false;
</script>
<div class="flex flex-col space-y-2 pb-10">
    <div class="relative px-8">
        <Header />
        <div style="height: 100%;" class="pb-2">
            <div class="h-32"></div>
            
            <Section name="pricing" sectionClass="my-16">
                <PricingHead>
                  <svelte:fragment slot="h2"
                    >TorchV Bot 提供开箱即用的SaaS服务</svelte:fragment>
                  <svelte:fragment slot="paragraph">开通Bot服务，上传文档，即可建立您专属的RAG知识对话系统，可通过H5、微信小程序对外服务。</svelte:fragment>
                </PricingHead>
                <div
                  class="space-y-8 lg:grid lg:grid-cols-3 sm:gap-6 xl:gap-10 lg:space-y-0 mx-32">
                  <PricingCard>
                    <PricingBodyHead>
                      <svelte:fragment slot="h3">试用版</svelte:fragment>
                      <svelte:fragment slot="paragraph"
                        >仅供测试使用。</svelte:fragment>
                      <svelte:fragment slot="price">
                        <span class="mr-2 text-5xl font-extrabold">免费</span>
                        <span class="text-gray-500 dark:text-gray-400"></span>
                      </svelte:fragment>
                    </PricingBodyHead>
                    <PricingItemWrapper>
                      <ul class="my-7 space-y-4">
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                          <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">
                            每分钟请求数（QPM）：10
                          </span>
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"
                          />
                          <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">50MB文件上传流量</span>
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                          <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">
                            赠送 ￥10 模型用量代金券
                          </span>
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                          <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">
                            知识库最大数量：2
                          </span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse line-through dark:text-primary-500">
                          <CheckCircleSolid
                            class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
                          <span
                            class="text-base font-normal leading-tight text-gray-500">一键嵌入Web端</span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse line-through dark:text-primary-500">
                          <CheckCircleSolid
                            class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
                          <span
                            class="text-base font-normal leading-tight text-gray-500">API访问</span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse line-through decoration-gray-500">
                          <CheckCircleSolid
                            class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
                          <span
                            class="text-base font-normal leading-tight text-gray-500">检索内容权限分级</span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse line-through decoration-gray-500">
                          <CheckCircleSolid
                            class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
                          <span
                            class="text-base font-normal leading-tight text-gray-500">智能洞察分析系统</span>
                        </li>
                      </ul>
                      <Button class="w-full">立即试用</Button>
                    </PricingItemWrapper>
                  </PricingCard>
            
                  <PricingCard>
                    <PricingBodyHead>
                      <svelte:fragment slot="h3">专业版</svelte:fragment>
                      <svelte:fragment slot="paragraph">适合企业/机构 内部使用。</svelte:fragment>
            
                      <svelte:fragment slot="price">
                        <span class="mr-2 text-5xl font-extrabold">￥36,000</span>
                        <span class="text-gray-500 dark:text-gray-400">/年</span>
                      </svelte:fragment>
                    </PricingBodyHead>
                    <PricingItemWrapper>
                      <!-- List -->
                      <ul class="my-7 space-y-4">
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                          <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">
                            每分钟请求数（QPM）：40
                          </span>
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                          <span
                            class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                          >
                            800MB文件上传流量
                          </span>
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                          >
                            赠送 ￥6,000 模型用量代金券
                          </span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500"
                            >知识库最大数量：6</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500"
                            >一键嵌入Web端</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500"
                            >API访问</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse line-through decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-gray-400 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500">检索内容权限分级</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse line-through decoration-gray-500">
                          <CheckCircleSolid
                            class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
                          <span
                            class="text-base font-normal leading-tight text-gray-500">智能洞察分析系统</span>
                        </li>
                      </ul>
                      <Button on:click={() => (defaultModal = true)} class="w-full">联系我们</Button>
                    </PricingItemWrapper>
                  </PricingCard>
            
                  <PricingCard>
                    <PricingBodyHead>
                      <svelte:fragment slot="h3">企业版</svelte:fragment>
                      <svelte:fragment slot="paragraph"
                        >适合企业/机构 对外服务。</svelte:fragment
                      >
                      <svelte:fragment slot="price">
                        <span class="mr-2 text-5xl font-extrabold">￥98,000</span>
                        <span class="text-gray-500 dark:text-gray-400">/年</span>
                      </svelte:fragment>
                    </PricingBodyHead>
                    <PricingItemWrapper>
                      <!-- List -->
                      <ul class="my-7 space-y-4">
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                          >
                          每分钟请求数（QPM）：90
                          </span>
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                          >
                            2GB文件上传流量
                          </span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500"
                            >赠送 ￥18,000 模型用量代金券</span
                          >
                        </li>
                        <li class="flex space-x-2 rtl:space-x-reverse">
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-primary-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                          >
                          知识库最大数量：15
                          </span>
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500"
                            >一键嵌入Web端</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500"
                            >API访问</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500">检索内容权限分级</span
                          >
                        </li>
                        <li
                          class="flex space-x-2 rtl:space-x-reverse decoration-gray-500"
                        >
                          <CheckCircleSolid
                            class="w-4 h-4 text-primary-600 dark:text-gray-500"
                          />
                          <span
                            class="text-base font-normal leading-tight text-gray-500">智能洞察分析系统</span
                          >
                        </li>
                      </ul>
                      <Button on:click={() => (defaultModal = true)} class="w-full">联系我们</Button>
                    </PricingItemWrapper>
                  </PricingCard>
                </div>
                
                <Modal title="" bind:open={defaultModal} autoclose size="sm">
                  <div class="flex justify-between mb-4 rounded-t sm:mb-5">
                    <div class="text-lg text-gray-900 md:text-xl dark:text-white">
                      <h3 class="font-semibold">您可以扫描下面的微信二维码进行咨询</h3>  
                    </div>
                  </div>
                  <!-- svelte-ignore a11y-missing-attribute -->
                  <img src="/images/yuanwai.jpg"/>
                  <div class="flex justify-between items-center">
                    <Button color="red">
                      关闭
                    </Button>
                  </div>
                </Modal>
                
              </Section>

              <Section name="faq">
                <h2 class="mb-8 text-4xl tracking-tight font-extrabold text-gray-900 dark:text-white">关于定价参数的解释</h2>
                <Faq>
                  <div class="pr-5">
                    <FaqItem>
                      <svelte:fragment slot="h3">什么是每分钟请求数（QPM）?</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">每分钟请求数（QPM），有时候也被称为RPM。指的是系统可提供的每分钟最大请求次数，一次请求包括用户输入、处理和开始输出，不包括输出的整个过程。
                        一般在多用户使用情况下QPM限制会更加明显。</p>
                    </FaqItem>
                    <FaqItem>
                      <svelte:fragment slot="h3">什么是文件上传流量?</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">TorchV Bot使用过程中需要用户上传文件、导入URL和粘贴文本作为知识库，然后与知识库进行对话。
                        这里指的”文件上传流量“指的是上传文件、导入URL和粘贴文本的总容量大小，一旦上传就计入”文件上传流量“，删除已经上传的文件不会缩减”文件上传流量“。
                    </p>

                    <p class="text-gray-500 dark:text-gray-400">
                        如您需要的上传文件流量超过对应版本的限定，
                        <!-- svelte-ignore a11y-missing-attribute -->
                        可<a class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"  on:click={() => (defaultModal = true)}>
                            联系我们</a>进行扩容。</p>
                    </FaqItem>
                    <FaqItem>
                      <svelte:fragment slot="h3">关于赠送模型用量代金券</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">TorchV Bot基于检索增强生成（RAG）技术，过程中需要让大模型进行生成，所以会消耗大模型调用费用。
                        我们调用的大模型厂商均为<a href="/docs/dev" class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline">
                            国内已备案大语言模型厂商</a>API，消费费用与各厂商价格保持一致。模型用量代金券可以作为大模型调用费用使用，赠送的模型用量代金券无法退款和转入下一周期。</p>
                    </FaqItem>
                    <FaqItem>
                      <svelte:fragment slot="h3">知识库数量代表什么?</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">
                    TorchV Bot允许在一个主账号内创建多个知识库，根据版本不同，允许创建的数量存在差异。创建不同的知识库主要有两个作用：
                    
                    </p>
                      <p class="text-gray-500 dark:text-gray-400">
                        1.可以为企业的多个不相关或弱相关应用创建知识库，每个应用可以绑定一个或多个不同的知识库。
                    如销售人员使用的应用可以绑定”销售话术知识库“、”产品知识库“和”客户案例知识库“等，而财务人员的应用可以绑定”销售知识库“、”财务知识库“等.
                      </p>
                      <p class="text-gray-500 dark:text-gray-400">2.各应用隔离知识库，也可以将企业内部的不同知识进行权限隔离，区分对外服务和对内（还可以区分各部门）服务。</p>
                    </FaqItem>
                  </div>
                  <div class="pl-5">
                    <FaqItem>
                      <svelte:fragment slot="h3">什么是一键嵌入Web端?</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">
                        目前试用TorchV Bot的方式最直接的就是使用系统自带的”知识运营“->”问答对话“，但这仅适用于内部人员。如果想让您的应用使用更广泛，最简单的方式就是使用”一键嵌入Web端“集成到您的官网、电商网站或内部B/S系统中。
                        使用方式非常简单，只需在系统的”应用开发“中找到”一键嵌入“的对接方式，复制一段js代码粘贴到您的站点`<head></head>`内即可。
                      </p>
                      <p class="text-gray-500 dark:text-gray-400">在您的站点页面的右下方会出现一个悬浮ICON，点击即可进行对话。</p>
                    </FaqItem>
                    <FaqItem>
                      <svelte:fragment slot="h3">关于检索内容权限分级</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">
                        与建立多个知识库进行访问权限隔离不同，检索内容权限分级更加安全。这里通过创建文件夹控制系统内不同角色的访问权限，但仅限于内部系统使用，不适合API对接的应用。
                      </p>
                      <p class="text-gray-500 dark:text-gray-400">该功能还在不断完善中</p>
                    </FaqItem>
                    <FaqItem>
                      <svelte:fragment slot="h3">关于智能洞察分析系统</svelte:fragment>
                      <p class="text-gray-500 dark:text-gray-400">
                        智能洞察分析系统有多个功能组成：主要包括意图识别功能、产品标签关联功能、实时推荐功能、问答分析功能，以及数据同步功能等。非常适合零售、电商、会员服务、医美、化妆品等对客服务型企业。</p>
                      <p class="text-gray-500 dark:text-gray-400">该功能暂不展现具体细节，详情可<a class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"  on:click={() => (defaultModal = true)}>
                        咨询我们</a>进行了解。</p>
                    </FaqItem>
                    
                  </div>
                </Faq>
              </Section>



        </div>
    </div>
    <Footer />
  </div>