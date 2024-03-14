<script>
    import { Section, BlogTemplate } from "flowbite-svelte-blocks";
    import Header from "$lib/Header.svelte";
    import Footer from "$lib/Footer.svelte";
    import { onMount } from "svelte";
    import { marked } from "marked";
    import { Breadcrumb, BreadcrumbItem, Hr } from "flowbite-svelte";
  
  
    let md = "";
  
    onMount(async function () {
        fetch("/md/whatis_torchv_bot.md")
            .then((response) => response.text())
            .then((data) => {
                md = data;
            })
            .catch((error) => {
                console.error("Error fetching markdown file:", error);
            });
    });
  
    let blog = {
        id: "what_is_torchv_bot",
        title: "什么是TorchV Bot ？",
        lead: "关于TorchV Bot的介绍。",
        author: {
            name: "员外",
            title: "TorchV CEO",
            profilePicture: "/images/team/yuanwai.png",
            href: "/",
        },
        date: "2024-01-26",
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
                <BreadcrumbItem>什么是TorchV Bot ？</BreadcrumbItem>
              </Breadcrumb>
            <Section name="blogTemplate">
                <article class="mx-auto w-full max-w-2xl format format-sm sm:format-base lg:format-lg format-blue dark:format-invert">
                    <BlogTemplate {blog} />
                </article>
            </Section>
            <Hr/>
            <Section>
                    <article class="prose mx-auto w-full format format-sm sm:format-base lg:format-lg format-blue dark:format-invert">
                        {@html marked.parse(md)}
                    </article>
            </Section>
        </div>
    </div>
    <Footer />
  </div>
  