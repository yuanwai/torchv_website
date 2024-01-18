<script>
    import { Button } from "flowbite-svelte";
    import { ArrowRightSolid } from "flowbite-svelte-icons";
    import {
        Section,
        HeroHeader,
    } from "flowbite-svelte-blocks";
</script>

<Section name="heroVisual" class="grid grid-cols-1 lg:grid-cols-12">
    <div class="mr-auto place-self-center lg:col-span-7">
      <HeroHeader
        h1Class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white"
        pClass="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 md:text-lg lg:text-xl dark:text-gray-400">
        <svelte:fragment slot="h1">使用RAG构建问答式业务</svelte:fragment>
        <svelte:fragment slot="paragraph">使用TorchV
          RAG，帮助您快速建立问答式业务应用。超强的语义理解能力，与传统智能问答技术相比，不再需要繁琐的知识库人工维护。</svelte:fragment>
        <a href="/docs/getting"
          ><Button size="xl" color="red" class="inline-flex items-center justify-center mr-3">现在就了解<ArrowRightSolid size="md" class="ml-2 -mr-1"/></Button></a>
        <a href="/try"><Button color="light" size="xl" class="inline-flex items-center justify-center">我要试用</Button></a>
      </HeroHeader>
    </div>
    <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
      <img src="/images/vt1.png" alt="mockup" width="400" />
    </div>
  </Section>