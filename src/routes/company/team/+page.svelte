<script>
    import { Section, TeamWrapper, TeamHeader, TeamBody, TeamItem, Github, Twitter } from "flowbite-svelte-blocks";
    import Header from "$lib/Header.svelte";
    import Footer from "$lib/Footer.svelte";

    let members = [
      {
        href: "/",
        src: "/images/team/yuanwai.png",
        alt: "yuanwai",
        name: "卢向东（员外）",
        jobTitle: "CEO | 创始人",
        description: "10年以上产研团队管理，5年以上AI产研团队负责人，多个著名项目销售负责人.",
        github: "https://github.com/yuanwai",
        twitter: "https://www.x.com/Tumeng05"
      },
      {
        href: "/",
        src: "/images/team/caidao.png",
        alt: "caidao",
        name: "肖玉民（菜刀）",
        jobTitle: "CTO | 创始人",
        description: "10年以上研发团队负责人，GVP开源项目（knife4j）Owner，全栈工程师+产品设计。",
        github: "https://github.com/xiaoymin",
        twitter: "https://www.x.com/xiaoymin"
      },
      {
        href: "/",
        src: "/images/team/abao.png",
        alt: "abao",
        name: "厉杭波（阿包）",
        jobTitle: "高级前端工程师 | 联创",
        description: "5年以上前端研发工作，多个超大型项目的主要前端工程师，个人喜欢Vue和React。",
        github: "https://github.com/xiaoymin",
        twitter: "https://www.x.com/lihehe1006"
      }
    ];
    
    </script>
    <Header />
    <div style="height: 100%;" class="overflow-scroll pb-16">
      <div class="h-32"></div>
    <Section name="team">
      <TeamWrapper>
        <TeamHeader>
          <svelte:fragment slot="label">核心团队</svelte:fragment>
          <p class="font-light text-gray-500 lg:mb-16 sm:text-xl dark:text-gray-400">简单、高效的团队，期待更多天才加入！</p>
        </TeamHeader>
        <TeamBody>
          {#each members as { href, src, alt, name, jobTitle, description, github, twitter }}
            <TeamItem {href} {src} {alt} {name} {jobTitle}>
              <p class="mt-3 mb-4 font-light text-gray-500 dark:text-gray-400">
                {description}
              </p>
              <svelte:fragment slot="social">
                <Github href={github} />
                <Twitter href={twitter} />
              </svelte:fragment>
            </TeamItem>
          {/each}
        </TeamBody>
      </TeamWrapper>
    </Section>
    <Footer/>
    </div>