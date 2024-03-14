<script>
    import { Button, Modal } from "flowbite-svelte";
    import { ArrowRightSolid } from "flowbite-svelte-icons";
    import { Section, HeroHeader,} from "flowbite-svelte-blocks";
    let defaultModal = false;
</script>

<Section name="heroVisual" class="grid grid-cols-1 lg:grid-cols-12 bg-yellow-200">
    <div class="mr-auto place-self-center lg:col-span-7">
      <HeroHeader
        h1Class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white"
        pClass="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 md:text-lg lg:text-xl dark:text-gray-400">
        <svelte:fragment slot="h1"><p>与非结构化数据建立对话</p></svelte:fragment>
        <svelte:fragment slot="paragraph">使用TorchV
          Bot 快速与各类型文档、扫描件、图片、音频建立问答式对话，让非结构化数据在您的业务中发挥巨大价值。</svelte:fragment>
        <a href="/docs/getting"
          ><Button size="xl" color="red" class="inline-flex items-center justify-center mr-3">现在了解<ArrowRightSolid size="md" class="ml-2 -mr-1"/></Button></a>
        <a href="/#"><Button on:click={() => (defaultModal = true)} color="light" size="xl" class=" inline-flex items-center justify-center">我要试用</Button></a>
      </HeroHeader>
    </div>
    <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
      <img src="/images/vt1.png" alt="mockup" width="400" />
    </div>
  </Section>
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