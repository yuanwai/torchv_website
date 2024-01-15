<script>
    import { Section, HeroHeader, FeatureDefault, FeatureItem } from "flowbite-svelte-blocks";
    import { ChartSolid, LandmarkSolid, BriefcaseSolid,DollarSolid, RocketSolid,CogOutline } from "flowbite-svelte-icons";
</script>

<Section name="feature" sectionClass="my-32">
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
          Plan it, create it, launch it. Collaborate seamlessly with all
          the organization and hit your marketing goals every month with our
          marketing plan.
        </svelte:fragment>
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><LandmarkSolid
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">易上手</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Protect your organization, devices and stay compliant with our
          structured workflows and custom permissions made for you.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><BriefcaseSolid
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">高准确率</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Auto-assign tasks, send Slack messages, and much more. Now power
          up with hundreds of new templates to help you get started.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><DollarSolid
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">访问权限可控</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Audit-proof software built for critical financial operations like
          month-end close and quarterly budgeting.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><RocketSolid
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">支持全量本地化部署</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Craft beautiful, delightful experiences for both marketing and
          product with real cross-company collaboration.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><CogOutline
            class="text-primary-600 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">配置灵活</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Keep your company’s lights on with customizable, iterative, and
          structured workflows built for all efficient teams and individual.</svelte:fragment
        >
      </FeatureItem>
    </FeatureDefault>
  </Section>