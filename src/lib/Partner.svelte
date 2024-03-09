<script>
    import { Section, Portfolio, PortfolioItem } from "flowbite-svelte-blocks";
   

    const portfolios = [
        {
            customer: "生产型企业",
            title: "操作指导助手",
            description:
                "海量存储即问即答，精准定位SOP，让错误减少17%",
            href: "/",
            linkTitle: "查看详情",
        },
        {
            customer: "项目型企业",
            title: "项目管理助手",
            description:
                "随时获取项目细节的When、Who、How",
            href: "/",
            linkTitle: "查看详情",
        },
        {
            customer: "博物馆/会展",
            title: "极速临展",
            description:
                "5分钟建立文物背后的故事",
            href: "/",
            linkTitle: "查看详情",
        },
        {
            customer: "博物馆/会展",
            title: "极速临展",
            description:
                "5分钟建立文物背后的故事",
            href: "/",
            linkTitle: "查看详情",
        },
        {
            customer: "博物馆/会展",
            title: "极速临展",
            description:
                "5分钟建立文物背后的故事",
            href: "/",
            linkTitle: "查看详情",
        },
        {
            customer: "博物馆/会展",
            title: "极速临展",
            description:
                "5分钟建立文物背后的故事",
            href: "/",
            linkTitle: "查看详情",
        },
    ];
</script>

<Section name="portfolio" sectionClass="bg-white dark:bg-gray-900 antialiased my-32">
    <Portfolio
        title="行业应用"
        subtitle="基于TorchV Bot的产品优势，助力各行各业提升业务能力" subtitleClass="mt-5 mb-10">

        {#each portfolios as item}
            <PortfolioItem {item} />
        {/each}
    </Portfolio>
</Section>

