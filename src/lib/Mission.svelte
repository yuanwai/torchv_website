<script>
    import { Section, ContentWithImage } from "flowbite-svelte-blocks";
</script>

<Section name="contentwithimg" sectionClass="my-16">
    <ContentWithImage>
      <svelte:fragment slot="h2"
        >创新 = 技术 + 需求</svelte:fragment
      >
      <p class="mb-6 mr-9">
        创新是增长的动力源泉，大语言模型（LLMs）和检索增强生成（RAG）等新技术，与您的需求结合，将带来全新的创新。
      </p>
      <p class="mb-6 mr-9">TorchV团队融合了优秀的软件工程师、AI算法科学家和经验丰富的业务架构师，我们为创新和优秀用户体验而战！</p>

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