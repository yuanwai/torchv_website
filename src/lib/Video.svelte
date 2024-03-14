<script>
    import { Video } from 'flowbite-svelte';
    import { ArrowRightSolid } from "flowbite-svelte-icons";
    import { Section, Cta } from "flowbite-svelte-blocks";
</script>
<Section name="ctawithimg" sectionClass="py-32">
    <Cta ctatype="image">
      <svelte:fragment slot="img">
        <Video src="/video/torchv.mp4" controls class="h-auto rounded-lg border border-gray-200 dark:border-gray-700" trackSrc="/video/torchv.mp4" />
        
      </svelte:fragment>
      <svelte:fragment slot="h2">从未如此简单</svelte:fragment>
      <p class="mb-6 font-light text-gray-500 md:text-lg dark:text-gray-400">只需五分钟，即可使用您的文档创建一个属于自己的助理机器人.</p>
      <p class="mb-6 font-light text-gray-500 md:text-lg dark:text-gray-400">与传统NLP机器人相比，效率提升百倍.</p>
      <a href="/docs" class="inline-flex items-center text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:focus:ring-primary-900">
        了解更多
        <ArrowRightSolid size="md" class="ml-2 -mr-1" />
      </a>
    </Cta>
  </Section>
   