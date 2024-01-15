<script>
  import { Button } from "flowbite-svelte";
  import { ArrowRightSolid,CheckCircleSolid } from "flowbite-svelte-icons";
  import { Section, PricingBodyHead, PricingCard, PricingItemWrapper,  ContentWithImage } from "flowbite-svelte-blocks";
  import { Faq, FaqItem, PricingHead, HeroHeader, TestimonialCard, TestimonialCardItem } from "flowbite-svelte-blocks";
  import Header from '$lib/Header.svelte';
  import Footer from '$lib/Footer.svelte';
  import Customers from '$lib/Customers.svelte';
  import Features from '$lib/Features.svelte'
  
</script>

<div class="flex flex-col space-y-2 pb-10">
  <div class="relative px-8">
    <Header/>
    <div style="height: 100%;" class="overflow-scroll pt-32">

      <Section name="heroVisual" class="grid grid-cols-1 lg:grid-cols-12">
        <div class="mr-auto place-self-center lg:col-span-7">
          <HeroHeader
            h1Class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white"
            pClass="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 md:text-lg lg:text-xl dark:text-gray-400">
            <svelte:fragment slot="h1">使用RAG构建问答式业务</svelte:fragment>
            <svelte:fragment slot="paragraph">使用TorchV RAG，快速构建问答式应用，无需繁琐人工维护。</svelte:fragment>
            <a href="/"
              ><Button size="xl" color="red" class="inline-flex items-center justify-center mr-3">现在了解<ArrowRightSolid size="md" class="ml-2 -mr-1"/></Button></a>
            <a href="/try"
              ><Button
                color="light"
                size="xl"
                class="inline-flex items-center justify-center">我要试用</Button></a>
          </HeroHeader>
        </div>
        <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
          <img src="/images/vt1.png" alt="mockup" width="400" />
        </div>
      </Section>

      <Customers/>

      <Section name="contentwithimg" sectionClass="my-16">
        <ContentWithImage>
          <svelte:fragment slot="h2">创新 = 需求 + 技术</svelte:fragment
          >
          <p class="mb-6 mr-9">
            保持创新是您持续盈利的原动力，TorchV团队期待与不同行业的合作伙伴共创新产品——使用您未满足的行业需求，和我们提供的大模型应用技术。
          </p>
          <p class="mb-6 mr-9">
            TorchV团队融合了优秀的软件工程团队、走在浪潮之巅的AI算法团队，以及经验丰富的业务架构师，我们为优秀用户体验而战！
          </p>

          <svelte:fragment slot="image">
            <img
              class="w-full rounded-lg"
              src="/images/office-long-1.png"
              alt="office content 1"
            />
            <img
              class="mt-4 w-full lg:mt-10 rounded-lg"
              src="/images/office-long-2.png"
              alt="office content 2"
            />
          </svelte:fragment>
        </ContentWithImage>
      </Section>

      <Features/>

      <Section
        name="ctawithimg"
        class="my-20 flex grid grid-cols-1 lg:grid-cols-2"
      >
        <div class="flex">
          <div class="flex-1 mx-10">
            <img src="/images/try.png" alt="dashboard" />
          </div>
          <div class="flex-1 ml-2 mr-16">
            <h1>百闻不如一“践”</h1>
            <p class="mb-6 font-light text-gray-500 md:text-lg dark:text-gray-400">
              我们希望得到关于您的信息，以及您在业务上的需求.
              只需填写很少的信息，之后我们会将试用账号发到您填写的邮箱.
            </p>
            <a
              href="/"
              class="inline-flex items-center text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:focus:ring-primary-900"
            >我要试用<ArrowRightSolid size="md" class="ml-2 -mr-1" />
            </a>
          </div>
        </div>
      </Section>

      <Section name="pricing" sectionClass="my-16">
        <PricingHead>
          <svelte:fragment slot="h2"
            >TorchV Bot 提供开箱即用的SaaS服务</svelte:fragment>
          <svelte:fragment slot="paragraph">开通Bot服务，上传文档，即可建立您专属的RAG知识对话系统，可通过H5、微信小程序对外服务。</svelte:fragment>
        </PricingHead>
        <div
          class="space-y-8 lg:grid lg:grid-cols-3 sm:gap-6 xl:gap-10 lg:space-y-0 mx-20">
          <PricingCard>
            <PricingBodyHead>
              <svelte:fragment slot="h3">基础版</svelte:fragment>
              <svelte:fragment slot="paragraph"
                >非常适合小团队内部使用。</svelte:fragment>
              <svelte:fragment slot="price">
                <span class="mr-2 text-5xl font-extrabold">￥19,800</span>
                <span class="text-gray-500 dark:text-gray-400">/年</span>
              </svelte:fragment>
            </PricingBodyHead>
            <PricingItemWrapper>
              <ul class="my-7 space-y-4">
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                  <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">
                    2个并发
                  </span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"
                  />
                  <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">200MB文件存储容量</span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"/>
                  <span class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400">
                    2000万tokens
                  </span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-gray-500"/>
                  <span class="text-base font-normal leading-tight text-gray-500">微信小程序、H5</span>
                </li>
                <li
                  class="flex space-x-2 rtl:space-x-reverse line-through dark:text-primary-500">
                  <CheckCircleSolid
                    class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
                  <span
                    class="text-base font-normal leading-tight text-gray-500">API访问</span>
                </li>
                <li
                  class="flex space-x-2 rtl:space-x-reverse line-through decoration-gray-500"
                >
                  <CheckCircleSolid
                    class="w-4 h-4 text-gray-400 dark:text-gray-500"
                  />
                  <span
                    class="text-base font-normal leading-tight text-gray-500"
                    >24×7 技术支持</span
                  >
                </li>
              </ul>
              <Button class="w-full">立即开通</Button>
            </PricingItemWrapper>
          </PricingCard>

          <PricingCard>
            <PricingBodyHead>
              <svelte:fragment slot="h3">标准版</svelte:fragment>
              <svelte:fragment slot="paragraph"
                >非常适合企业/机构内部使用。</svelte:fragment
              >
              <svelte:fragment slot="price">
                <span class="mr-2 text-5xl font-extrabold">￥36,800</span>
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
                    5个并发
                  </span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"
                  />
                  <span
                    class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                  >
                    500MB文件存储容量
                  </span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"
                  />
                  <span
                    class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                  >
                    5000万tokens
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
                    >微信小程序、H5</span
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
                    class="text-base font-normal leading-tight text-gray-500"
                    >24×7 技术支撑</span
                  >
                </li>
              </ul>
              <Button class="w-full">立即开通</Button>
            </PricingItemWrapper>
          </PricingCard>

          <PricingCard>
            <PricingBodyHead>
              <svelte:fragment slot="h3">专业版</svelte:fragment>
              <svelte:fragment slot="paragraph"
                >适合企业/机构对外服务.</svelte:fragment
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
                    20个并发
                  </span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"
                  />
                  <span
                    class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                  >
                    2GB文件存储容量
                  </span>
                </li>
                <li class="flex space-x-2 rtl:space-x-reverse">
                  <CheckCircleSolid
                    class="w-4 h-4 text-primary-600 dark:text-primary-500"
                  />
                  <span
                    class="text-base font-normal leading-tight text-gray-500 dark:text-gray-400"
                  >
                    微信小程序、H5、APP
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
                    >2亿tokens</span
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
                    class="text-base font-normal leading-tight text-gray-500"
                    >24×7 技术支持</span
                  >
                </li>
              </ul>
              <Button class="w-full">立即开通</Button>
            </PricingItemWrapper>
          </PricingCard>
        </div>
      </Section>

      <Section name="testimonial" sectionClass="my-16">
        <TestimonialCard>
          <svelte:fragment slot="header">
            <h2
              class="mb-4 text-4xl tracking-tight font-extrabold text-gray-900 dark:text-white"
            >
              来自客户的声音
            </h2>
            <p
              class="mb-8 font-light text-gray-500 lg:mb-16 sm:text-xl dark:text-gray-400"
            >
              TorchV系列产品从一开始就和客户进行共创，正是他们的积极参与以及在不同行业地应用，才让我们有了更多将产品技术与实际业务需求结合的经验。
            </p>
          </svelte:fragment>
        </TestimonialCard>
        <div class="grid mb-8 lg:mb-12 lg:grid-cols-2">
          <TestimonialCardItem>
            <svelte:fragment slot="h3"
              >Speechless with how easy this was to integrate</svelte:fragment
            >
            <p class="my-4">
              "I recently got my hands on Flowbite Pro, and holy crap, I'm
              speechless with how easy this was to integrate within my
              application. Most templates are a pain, code is scattered, and
              near impossible to theme.
            </p>
            <p class="my-4">
              Flowbite has code in one place and I'm not joking when I say it
              took me a matter of minutes to copy the code, customise it and
              integrate within a Laravel + Vue application.
            </p>
            <p class="my-4">
              If you care for your time, I hands down would go with this."
            </p>
            <svelte:fragment slot="caption">
              <img
                class="w-9 h-9 rounded-full"
                src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/karen-nelson.png"
                alt="karen profile"
              />
              <div class="space-y-0.5 font-medium dark:text-white text-left">
                <div>Bonnie Green</div>
                <div
                  class="text-sm font-light text-gray-500 dark:text-gray-400"
                >
                  Developer at Open AI
                </div>
              </div>
            </svelte:fragment>
          </TestimonialCardItem>
          <TestimonialCardItem>
            <svelte:fragment slot="h3"
              >Solid foundation for any project</svelte:fragment
            >
            <p class="my-4">
              "FlowBite provides a robust set of design tokens and components
              based on the popular Tailwind CSS framework. From the most used UI
              components like forms and navigation bars to the whole app screens
              designed both for desktop and mobile, this UI kit provides a solid
              foundation for any project.
            </p>
            <p class="my-4">
              Designing with Figma components that can be easily translated to
              the utility classes of Tailwind CSS is a huge timesaver!"
            </p>
            <svelte:fragment slot="caption">
              <img
                class="w-9 h-9 rounded-full"
                src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/roberta-casas.png"
                alt="robert profile"
              />
              <div class="space-y-0.5 font-medium dark:text-white text-left">
                <div>Roberta Casas</div>
                <div
                  class="text-sm font-light text-gray-500 dark:text-gray-400"
                >
                  Lead designer at Dropbox
                </div>
              </div>
            </svelte:fragment>
          </TestimonialCardItem>
          <TestimonialCardItem>
            <svelte:fragment slot="h3"
              >Mindblowing workflow and variants</svelte:fragment
            >
            <p class="my-4">
              "As someone who mainly designs in the browser, I've been a casual
              user of Figma, but as soon as I saw and started playing with
              FlowBite my mind was 🤯.
            </p>
            <p class="my-4">
              Everything is so well structured and simple to use (I've learnt so
              much about Figma by just using the toolkit).
            </p>
            <p class="my-4">
              Aesthetically, the well designed components are beautiful and will
              undoubtedly level up your next application."
            </p>
            <svelte:fragment slot="caption">
              <img
                class="w-9 h-9 rounded-full"
                src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/jese-leos.png"
                alt="jese leos profile"
              />
              <div class="space-y-0.5 font-medium dark:text-white text-left">
                <div>Jese Leos</div>
                <div
                  class="text-sm font-light text-gray-500 dark:text-gray-400"
                >
                  Software Engineer at Facebook
                </div>
              </div>
            </svelte:fragment>
          </TestimonialCardItem>
          <TestimonialCardItem>
            <svelte:fragment slot="h3">Efficient Collaborating</svelte:fragment>
            <p class="my-4">
              "This is a very complex and beautiful set of elements. Under the
              hood it comes with the best things from 2 different worlds: Figma
              and Tailwind.
            </p>
            <p class="my-4">
              You have many examples that can be used to create a fast prototype
              for your team."
            </p>
            <svelte:fragment slot="caption">
              <img
                class="w-9 h-9 rounded-full"
                src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/joseph-mcfall.png"
                alt="joseph profile"
              />
              <div class="space-y-0.5 font-medium dark:text-white text-left">
                <div>Joseph McFall</div>
                <div
                  class="text-sm font-light text-gray-500 dark:text-gray-400"
                >
                  CTO at Google
                </div>
              </div>
            </svelte:fragment>
          </TestimonialCardItem>
        </div>
        <div class="text-center">
          <a
            href="/"
            class="py-2.5 px-5 mr-2 mb-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700"
            >Show more...</a
          >
        </div>
      </Section>

      <Section name="faq" sectionClass="my-16">
        <h2
          class="mb-8 text-4xl tracking-tight font-extrabold text-gray-900 dark:text-white"
        >
          常见问题
        </h2>
        <Faq>
          <div>
            <FaqItem>
              <svelte:fragment slot="h3">你们有哪些交付方式？</svelte:fragment>
              <p class="text-gray-500 dark:text-gray-400">
                You will have access to download the full Figma project
                including all of the pages, the components, responsive pages,
                and also the icons, illustrations, and images included in the
                screens.
              </p>
            </FaqItem>
            <FaqItem>
              <svelte:fragment slot="h3"
                >你们的产品支持二次开发和其他终端的对接吗？</svelte:fragment
              >
              <p class="text-gray-500 dark:text-gray-400">
                Once you have purchased either the design, code, or both
                packages, you will have access to all of the future updates
                based on the roadmap, free of charge.
              </p>
            </FaqItem>
            <FaqItem>
              <svelte:fragment slot="h3">可以按月支付吗？</svelte:fragment>
              <p class="text-gray-500 dark:text-gray-400">
                We're aware of the importance of well qualified support, that is
                why we decided that support will only be provided by the authors
                that actually worked on this project.
              </p>
              <p class="text-gray-500 dark:text-gray-400">
                Feel free to <a
                  href="/"
                  class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"
                  target="_blank"
                  rel="noreferrer">contact us</a
                > and we'll help you out as soon as we can.
              </p>
            </FaqItem>
            <FaqItem>
              <svelte:fragment slot="h3"
                >如果我需要私有化部署，那可以享受你们后续的更新迭代吗？</svelte:fragment
              >
              <p class="text-gray-500 dark:text-gray-400">
                You can use Windster for an unlimited amount of projects,
                whether it's a personal website, a SaaS app, or a website for a
                client. As long as you don't build a product that will directly
                compete with Windster either as a UI kit, theme, or template,
                it's fine.
              </p>
              <p class="text-gray-500 dark:text-gray-400">
                Find out more information by <a
                  href="/"
                  class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"
                  >reading the license</a
                >.
              </p>
            </FaqItem>
          </div>
          <div>
            <FaqItem>
              <svelte:fragment slot="h3"
                >我想在我的行业和你们进行共创，应该如何开始？</svelte:fragment
              >
              <p class="text-gray-500 dark:text-gray-400">
                The free updates that will be provided is based on the <a
                  href="/"
                  class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"
                  >roadmap</a
                > that we have laid out for this project. It is also possible that
                we will provide extra updates outside of the roadmap as well.
              </p>
            </FaqItem>
            <FaqItem>
              <svelte:fragment slot="h3"
                >你们的产品迭代节奏是怎么样的？后续有哪些新产品发布计划？</svelte:fragment
              >
              <p class="text-gray-500 dark:text-gray-400">
                Generally, it is accepted to use Windster in open-source
                projects, as long as it is not a UI library, a theme, a
                template, a page-builder that would be considered as an
                alternative to Windster itself.
              </p>
              <p class="text-gray-500 dark:text-gray-400">
                With that being said, feel free to use this design kit for your
                open-source projects.
              </p>
              <p class="text-gray-500 dark:text-gray-400">
                Find out more information by <a
                  href="/"
                  class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"
                  >reading the license</a
                >.
              </p>
            </FaqItem>
          </div>
        </Faq>
      </Section>
      <Footer/>
    </div>
  </div>
</div>
