<script>
    import { Section, TeamWrapper, TeamHeader, TeamBody, TeamItem, Github, Twitter, ContentWithImage } from "flowbite-svelte-blocks";
    import Header from "$lib/Header.svelte";
    import Footer from "$lib/Footer.svelte";

    let members = [
      {
        href: "/",
        src: "/images/team/yuanwai.png",
        alt: "yuanwai",
        name: "员外",
        jobTitle: "CEO | 创始人",
        description: "行业老兵，负责公司的产品设计、市场营销和产品销售等工作。",
        github: "https://github.com/yuanwai",
        twitter: "https://www.x.com/Tumeng05"
      },
      {
        href: "/",
        src: "/images/team/caidao.png",
        alt: "caidao",
        name: "菜刀",
        jobTitle: "CTO | 创始人",
        description: "产品研发团队负责人，GVP开源项目（knife4j）Owner。",
        github: "https://github.com/xiaoymin",
        twitter: "https://www.x.com/xiaoymin"
      },
      {
        href: "/",
        src: "/images/team/abao.png",
        alt: "abao",
        name: "阿包",
        jobTitle: "高级前端工程师 | 联创",
        description: "前端工程师，个人喜欢Vue，但是React/Svelte来者不拒。",
        github: "",
        twitter: "https://www.x.com/lihehe1006"
      }
    ];
    
    </script>
    <Header />
    <div style="height: 100%;" class="overflow-scroll pb-16">
      <div class="h-32"></div>

      <Section name="contentwithimg" sectionClass="my-16">
        <ContentWithImage>
          <svelte:fragment slot="h2">关于我们</svelte:fragment
          >
          <p class="mb-6 mr-9">
            杭州萌嘉网络科技有限公司成立于2020年,总部位于中国浙江省杭州市。我们致力于为各行业企业提供先进的AI应用产品,为客户创造更智能,更高效的业务能力。旗下拥有AI应用品牌—— TorchV 。
          </p>
          <p class="mb-6 mr-9">TorchV团队融合了优秀的软件工程师、AI算法科学家和经验丰富的业务架构师，我们为创新和优秀用户体验而战！</p>
    
          <svelte:fragment slot="image">
            <img
              class="w-full rounded-lg"
              src="/images/team/office2.png"
              alt="office content 1"
            />
            <img
              class="mt-4 w-full lg:mt-10 rounded-lg"
              src="/images/team/office1.png"
              alt="office content 2"
            />
          </svelte:fragment>
        </ContentWithImage>
      </Section>


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