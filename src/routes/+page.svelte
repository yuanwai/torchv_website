<script>
  import Customers from "$lib/Customers.svelte";
  import Features from "$lib/Features.svelte";
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
  import Pricing from "$lib/Pricing.svelte";
  import Testimonial from "$lib/Testimonial.svelte";
  import Faq from "$lib/Faq.svelte";
  import IndexSection from "$lib/IndexSection.svelte";
  import Mission from "$lib/Mission.svelte";
  import ShowCast from "$lib/ShowCast.svelte";
  import Partner from "$lib/Partner.svelte";
  import Video from "$lib/Video.svelte";
  import { Hr } from "flowbite-svelte";
</script>

<div class="flex flex-col space-y-2 pb-10">
  <div class="relative px-8">
    <Header />
    <div style="height: 100%;" class="pb-16">
      <div class="h-32 "></div>
      <!-- 首屏 -->
      <IndexSection />
      <!-- 视频 -->
      <Video/>
      <!-- 客户展示 -->
      <!-- <Customers /> -->
      <!-- 特性 -->
      <Features />
   
      <Partner/>
      <!-- 快照和试用 -->
      <ShowCast />
      <Hr/>
      <!-- 价格 -->
      <Pricing />
      <!-- 使命 -->
      <Mission />
      <!-- FAQ -->
      <!-- <Faq /> -->
      <!-- 页脚 -->
      <Footer />
    </div>
  </div>
</div>
