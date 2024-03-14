<script>
    import { Section, Portfolio, PortfolioItem } from "flowbite-svelte-blocks";
   

    const portfolios = [
        {
            customer: "工业制造企业",
            title: "掌上操作指南",
            description:
                "海量存储即问即答，精准定位SOP，让错误减少17%",
            href: "/docs/cases",
            linkTitle: "查看详情",
        },
        {
            customer: "项目型企业",
            title: "项目管理助手",
            description:
                "随时获取项目细节的When、Who、How",
            href: "/docs/cases",
            linkTitle: "查看详情",
        },
        {
            customer: "文博/会展",
            title: "极速临展",
            description:
                "5分钟创建文物/展品背后的故事",
            href: "/docs/cases",
            linkTitle: "查看详情",
        }
    ];


    const portfolios1 = [
        {
            customer: "医美护理",
            title: "会员和产品推荐",
            description:
                "细心照顾您的会员，提供个性护理建议和产品导购",
            href: "/docs/cases",
            linkTitle: "查看详情",
        },
        {
            customer: "家电&汽车",
            title: "售后服务",
            description:
                "7x24解决使用咨询和售后问题",
            href: "/docs/cases",
            linkTitle: "查看详情",
        },
        {
            customer: "零售/电商",
            title: "客户支持辅助",
            description:
                "客户回复内容辅助，客服人员的Coplit",
            href: "/docs/cases",
            linkTitle: "查看详情",
        },
    ];
</script>

<Section sectionClass="bg-white dark:bg-gray-900 antialiased my-10">
    <Portfolio 
        title="行业应用" 
        subtitle="基于TorchV Bot的产品优势，助力各行各业提升业务能力" subtitleClass="mt-5 mb-10">

        {#each portfolios as item}
            <PortfolioItem {item}/>
        {/each}
    </Portfolio>
</Section>

<Section sectionClass="bg-white dark:bg-gray-900 antialiased my-32">
    <Portfolio 
        title="" 
        subtitle="">

        {#each portfolios1 as item}
            <PortfolioItem {item} />
        {/each}
    </Portfolio>
</Section>

