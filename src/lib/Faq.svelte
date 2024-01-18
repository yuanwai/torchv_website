<script>
    import {
        Section,
        Faq,
        FaqItem,
    } from "flowbite-svelte-blocks";
</script>

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
            我们的交付方式一般分为两种：
          </p>
          <p class="text-gray-500 dark:text-gray-400">1.SaaS方式交付，开箱即用，按需订阅；</p>
          <p class="text-gray-500 dark:text-gray-400">2.本地化部署交付，一次性部署，按项目方式交付。</p>
        </FaqItem>
        <FaqItem>
          <svelte:fragment slot="h3"
            >你们的产品支持二次开发和其他终端的对接吗？</svelte:fragment
          >
          <p class="text-gray-500 dark:text-gray-400">
            从标准版开始既支持API调用，可用于与您原有应用集成，
          </p>
          <p class="text-gray-500 dark:text-gray-400">
            也可用于其他终端设备对接。
          </p>
        </FaqItem>
        <FaqItem>
          <svelte:fragment slot="h3">可以按月支付吗？</svelte:fragment>
          <p class="text-gray-500 dark:text-gray-400">
            我们的SaaS服务支持按月支付，年费立减两个月的费用。
          </p>
          <p class="text-gray-500 dark:text-gray-400">
            具体的订阅信息可点击 <a href="/"
              class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"
              target="_blank" rel="noreferrer">这里</a> 查看详细解读.
          </p>
        </FaqItem>
        <FaqItem>
          <svelte:fragment slot="h3"
            >如果我需要私有化部署，那可以享受你们后续的更新迭代吗？</svelte:fragment
          >
          <p class="text-gray-500 dark:text-gray-400">
            私有化部署可按项目方式签约，具体更新细节，可以case by case。
          </p>
          <p class="text-gray-500 dark:text-gray-400">
            您可以通过 <a href="/" class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline">TorchV RAG应用私有化部署方案</a>了解更多内容.
          </p>
        </FaqItem>
      </div>
      <div>
        <FaqItem>
          <svelte:fragment slot="h3"
            >我有行业需求，如何与你们进行产品共创？</svelte:fragment
          >
          <p class="text-gray-500 dark:text-gray-400">
            首先您可以阅读我们的 <a
              href="/"
              class="font-medium underline text-primary-600 dark:text-primary-500 hover:no-underline"
              >合作伙伴指南</a>，了解我们对合作伙伴的要求，及如何开展的具体流程.
          </p>
        </FaqItem>
        <FaqItem>
          <svelte:fragment slot="h3"
            >你们的产品迭代节奏是怎么样的？后续有哪些新产品发布计划？</svelte:fragment
          >
          <p class="text-gray-500 dark:text-gray-400">
            目前暂无具体信息.
          </p>
          <p class="text-gray-500 dark:text-gray-400">
            请持续关注TorchV，春节后将会给出进一步计划.
          </p>
        </FaqItem>
      </div>
    </Faq>
  </Section>