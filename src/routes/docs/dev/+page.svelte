<script>
    import { Section, BlogTemplate } from "flowbite-svelte-blocks";
    import Header from "$lib/Header.svelte";
    import Footer from "$lib/Footer.svelte";
    import { onMount } from "svelte";
    import { marked } from "marked";
    import { Hr,Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

    let md = "";

    onMount(async function () {
        fetch("/md/apidoc.md")
            .then((response) => response.text())
            .then((data) => {
                md = data;
            })
            .catch((error) => {
                console.error("Error fetching markdown file:", error);
            });
    });

    let blog = {
        id: "torchv_bot_apidoc",
        title: "TorchV Bot API对接手册",
        lead: "本手册旨在介绍TorchV Bot的API开发手册，针对使用TorchV Bot能力开发自有应用的技术人员。",
        author: {
            name: "八一菜刀",
            title: "TorchV CTO",
            profilePicture: "/images/team/caidao.png",
            href: "/",
        },
        date: "2024-03-01",
        isoDate: "2022-02-08",
        content: "",
    }; 
</script>

<div class="flex flex-col space-y-2 pb-10">
    <div class="relative px-8">
        <Header />
        <div style="height: 100%;" class="pb-2">
            <div class="h-32"></div>
            <Breadcrumb aria-label="Default breadcrumb example">
                <BreadcrumbItem href="/" home>首页</BreadcrumbItem>
                <BreadcrumbItem href="/docs">文档</BreadcrumbItem>
                <BreadcrumbItem>TorchV Bot API对接手册</BreadcrumbItem>
              </Breadcrumb>
            <Section name="blogTemplate" classSection="pt-8 pb-2 lg:pt-16 lg:pb-4 bg-white dark:bg-gray-900">
                <article class="mx-auto w-full max-w-2xl format format-sm sm:format-base lg:format-lg format-blue dark:format-invert">
                    <BlogTemplate {blog} />
                </article>
            </Section>
            <Hr/>
            <Section>
                    <article class="prose mx-auto w-full max-w-2xl format format-sm sm:format-base lg:format-lg format-blue dark:format-invert">
                        {@html marked.parse(md)}
                    </article>
            </Section>
        </div>
    </div>
    <Footer />
</div>