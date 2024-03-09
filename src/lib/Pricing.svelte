<script>
import { Button } from "flowbite-svelte";
import { Section, PricingBodyHead, PricingCard, PricingItemWrapper, PricingHead } from "flowbite-svelte-blocks";
import { CheckCircleSolid } from "flowbite-svelte-icons";
</script>

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
                class="text-base font-normal leading-tight text-gray-500">API访问</span>
            </li>
            <li
              class="flex space-x-2 rtl:space-x-reverse line-through decoration-gray-500">
              <CheckCircleSolid
                class="w-4 h-4 text-gray-400 dark:text-gray-500"/>
              <span
                class="text-base font-normal leading-tight text-gray-500">检索内容权限分级</span>
            </li>
          </ul>
          <Button class="w-full">立即试用</Button>
        </PricingItemWrapper>
      </PricingCard>

      <PricingCard>
        <PricingBodyHead>
          <svelte:fragment slot="h3">标准版</svelte:fragment>
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
          </ul>
          <Button class="w-full">立即开通</Button>
        </PricingItemWrapper>
      </PricingCard>

      <PricingCard>
        <PricingBodyHead>
          <svelte:fragment slot="h3">专业版</svelte:fragment>
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
          </ul>
          <Button class="w-full">立即开通</Button>
        </PricingItemWrapper>
      </PricingCard>
    </div>
  </Section>