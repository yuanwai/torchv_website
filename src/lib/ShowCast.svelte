<script>
    import { ArrowRightSolid } from "flowbite-svelte-icons";
    import { Section, Cta } from "flowbite-svelte-blocks";
</script>
<Section name="ctawithimg">
    <Cta ctatype="image">
      <svelte:fragment slot="img">
        <img class="w-full dark:hidden shadow-xl dark:shadow-gray-800" src="/images/try.png" alt="dashboard" />
        
      </svelte:fragment>
      <svelte:fragment slot="h2">百闻不如一“践”</svelte:fragment>
      <p class="mb-6 font-light text-gray-500 md:text-lg dark:text-gray-400">我们希望得到关于您的信息, 以及您在业务上的需求, 只需填写很少的信息, 之后我们会将试用账号发到您填写的邮箱.</p>
      <a href="/try" class="inline-flex items-center text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:focus:ring-primary-900">
        现在试用
        <ArrowRightSolid size="md" class="ml-2 -mr-1" />
      </a>
    </Cta>
  </Section>