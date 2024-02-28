<script>
    import { Section, HeroHeader, FeatureDefault, FeatureItem } from "flowbite-svelte-blocks";
    import { ChartSolid, LandmarkSolid, BriefcaseSolid,DollarSolid, RocketSolid,CogOutline } from "flowbite-svelte-icons";
</script>

<Section name="feature" sectionClass="py-32  bg-slate-100">
    <HeroHeader
      class="max-w-screen-md mb-8 lg:mb-16"
      h2Class="mb-4 text-4xl tracking-tight font-extrabold text-gray-900 dark:text-white"
      pClass="text-gray-500 sm:text-xl dark:text-gray-400">
      <svelte:fragment slot="h2">为什么选择TorchV RAG应用</svelte:fragment>
      <svelte:fragment slot="paragraph">6大关键产品技术特性一览</svelte:fragment>
    </HeroHeader>
    <FeatureDefault>
      <FeatureItem>
        <svelte:fragment slot="icon"><ChartSolid class="text-primary-600 dark:text-primary-300"/></svelte:fragment>
        <svelte:fragment slot="h3">开箱即用</svelte:fragment>
        <svelte:fragment slot="paragraph">
          <p class="pr-6">
          TorchV RAG 为您提供开箱即用服务。只需开通服务，无需专业培训，即可在几分钟内轻松完成生产级咨询服务机器人（Bot）搭建.
        </p>
        </svelte:fragment>
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"><LandmarkSolid
            class="text-primary-600 dark:text-primary-300"/></svelte:fragment>
        <svelte:fragment slot="h3">高精准度</svelte:fragment>
        <svelte:fragment slot="paragraph">
          <p class="pr-6">
          TorchV 采用自研RAG架构，在各个环节进行优化提升，配合自研的幂等分类器、执行器、重排序等，让RAG意图理解能力、召回准确度极大提升。
          </p>
        </svelte:fragment>
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><BriefcaseSolid
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">轻松扩展“+AI”</svelte:fragment>
        <svelte:fragment slot="paragraph">
          <p class="pr-6">我们提供高效扩展API和技术手册，可被您的原有应用集成，轻松将您的应用扩展成“+AI”。</p></svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><DollarSolid
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">访问权限可控</svelte:fragment>
        <svelte:fragment slot="paragraph"><p class="pr-6">
          可对知识内容进行访问权限控制，让敏感仅对指定人员开放，以保护您的企业数据安全。</p>
        </svelte:fragment>
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><RocketSolid
            class="text-primary-600 dark:text-primary-300"/></svelte:fragment>
        <svelte:fragment slot="h3">支持全量本地化部署</svelte:fragment>
        <svelte:fragment slot="paragraph"><p class="pr-6">
          我们提倡SaaS订阅，但依然提供全量本地化部署，包括大语言模型、RAG和应用，满足政府和特定企业的安全要求。</p>
          </svelte:fragment>
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"><CogOutline
            class="text-primary-600 dark:text-primary-300"/></svelte:fragment>
        <svelte:fragment slot="h3">配置灵活</svelte:fragment>
        <svelte:fragment slot="paragraph"><p class="pr-6">
          TorchV RAG提供丰富的配置操作界面，使用者可在实际使用中调整各类参数来适配业务场景。主要参数包括语义和关键词检索权重，是否让LLM兜底回复等。</p>
          </svelte:fragment>
      </FeatureItem>
    </FeatureDefault>
  </Section>