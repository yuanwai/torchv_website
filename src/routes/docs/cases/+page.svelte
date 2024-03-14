<script>
    import { Section, BlogTemplate } from "flowbite-svelte-blocks";
    import Header from "$lib/Header.svelte";
    import Footer from "$lib/Footer.svelte";
    import { onMount } from "svelte";
    import { marked } from "marked";
    import { Hr } from "flowbite-svelte";
  
  
    let md = "";
  
    onMount(async function () {
        fetch("/md/cases.md")
            .then((response) => response.text())
            .then((data) => {
                md = data;
            })
            .catch((error) => {
                console.error("Error fetching markdown file:", error);
            });
    });
  
    let blog = {
        id: "torchv_bot_cases",
        title: "TorchV Bot 用户案例介绍",
        lead: "对TorchV Bot使用场景的一些简介。",
        author: {
            name: "员外",
            title: "TorchV CEO",
            profilePicture: "/images/team/yuanwai.png",
            href: "/",
        },
        date: "2024-03-12",
        isoDate: "2022-02-08",
        content: "",
    }; 
  </script>
  
  <div class="flex flex-col space-y-2 pb-10">
    <div class="relative px-8">
        <Header />
        <div style="height: 100%;" class="pb-2">
            <div class="h-32"></div>
            <Section name="blogTemplate">
                <article class="mx-auto w-full max-w-2xl format format-sm sm:format-base lg:format-lg format-blue dark:format-invert">
                    <BlogTemplate {blog} />
                </article>
            </Section>
            <Hr/>
            <Section>
                    <article class="prose mx-auto w-full  format format-sm sm:format-base lg:format-lg format-blue dark:format-invert">
                        {@html marked.parse(md)}
                    </article>
            </Section>
        </div>
    </div>
    <Footer />
  </div>
  