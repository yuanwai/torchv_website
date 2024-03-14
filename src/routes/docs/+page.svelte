<script>
    import { Section, Cta , ArticleAuthor, ArticleBody, ArticleHead, ArticleWrapper, BlogHead, BlogBodyWrapper } from 'flowbite-svelte-blocks';
    import { VideoSolid, ArrowRightOutline, ArrowRightSolid, NewspaperSolid } from 'flowbite-svelte-icons';
    import Header from "$lib/Header.svelte";
    import Footer from "$lib/Footer.svelte";
</script>
<div class="flex flex-col space-y-2 pb-10">
    <div class="relative px-8">
        <Header />
        <div style="height: 100%;" class="pb-16">
            <div class="h-32"></div>

            <Section name="blog">
                <BlogHead>
                    <svelte:fragment slot="h2">TorchV文档库</svelte:fragment>
                    <svelte:fragment slot="paragraph">
                        <p
                            class="font-light text-gray-500 sm:text-xl dark:text-gray-400"
                        >
                            在这里您可以找到关于TorchV的产品和技术文档，以及我们及合作伙伴发布的Blog.
                        </p>
                    </svelte:fragment>
                </BlogHead>
                <BlogBodyWrapper>
                    <ArticleWrapper>
                        <ArticleHead>
                            <span
                                class="bg-primary-100 text-primary-800 text-xs font-medium inline-flex items-center px-2.5 py-0.5 rounded dark:bg-primary-200 dark:text-primary-800"
                            >
                                <VideoSolid size="xs" class="mr-1" />
                                Tutorial
                            </span>
                            <span class="text-sm">2024-03-05</span>
                        </ArticleHead>
                        <ArticleBody>
                            <svelte:fragment slot="h2"
                                ><a href="/docs/manual">TorchV Bot 用户操作手册</a
                                ></svelte:fragment
                            >
                            <svelte:fragment slot="paragraph">
                                <p
                                    class="mb-5 font-light text-gray-500 dark:text-gray-400"
                                >
                                    本手册旨在介绍TorchV
                                    Bot用户端的业务及操作流程，以便用户能更有效地进行业务处理和操作。针对使用TorchV
                                    Bot产品的运营人员和技术人员。
                                </p>
                            </svelte:fragment>
                        </ArticleBody>
                        <ArticleAuthor>
                            <svelte:fragment slot="author">
                                <img
                                    class="w-10 h-10 rounded-full"
                                    src="/images/team/caidao.png"
                                    alt="Jese Leos avatar"
                                />
                                <span class="font-medium dark:text-white">
                                    八一菜刀
                                </span>
                            </svelte:fragment>
                            <a
                                href="/docs/manual"
                                class="inline-flex items-center font-medium text-primary-600 dark:text-primary-500 hover:underline"
                            >
                                点击查看
                                <ArrowRightOutline size="sm" class="ml-2" />
                            </a>
                        </ArticleAuthor>
                    </ArticleWrapper>

                    <ArticleWrapper>
                        <ArticleHead>
                            <span
                                class="bg-primary-100 text-primary-800 text-xs font-medium inline-flex items-center px-2.5 py-0.5 rounded dark:bg-primary-200 dark:text-primary-800"
                            >
                                <NewspaperSolid size="xs" class="mr-1" />
                                DevGuide
                            </span>
                            <span class="text-sm">2024-03-12</span>
                        </ArticleHead>
                        <ArticleBody>
                            <svelte:fragment slot="h2"
                                ><a href="/">TorchV Bot 开放接口（API）说明</a
                                ></svelte:fragment
                            >
                            <svelte:fragment slot="paragraph">
                                <p
                                    class="mb-5 font-light text-gray-500 dark:text-gray-400"
                                >
                                    针对TorchV应用中的场景，将接口文档固化进行迭代发布更新，服务对接使用TorchV产品的技术&客户进行使用。
                                </p>
                            </svelte:fragment>
                        </ArticleBody>
                        <ArticleAuthor>
                            <svelte:fragment slot="author">
                                <img
                                    class="w-10 h-10 rounded-full"
                                    src="/images/team/caidao.png"
                                    alt="Bonnie Green avatar"
                                />
                                <span class="font-medium dark:text-white">
                                    八一菜刀
                                </span>
                            </svelte:fragment>
                            <a
                                href="/docs/dev"
                                class="inline-flex items-center font-medium text-primary-600 dark:text-primary-500 hover:underline"
                            >
                                点击查看
                                <ArrowRightOutline size="sm" class="ml-2" />
                            </a>
                        </ArticleAuthor>
                    </ArticleWrapper>

                
                </BlogBodyWrapper>
            </Section>
            <Section name="ctawithimg" sectionClass="my-32">
                <Cta ctatype="image">
                    <svelte:fragment slot="img">
                        <img
                            class="w-full dark:hidden"
                            src="/images/docs/manual/torchvbot_arc.png"
                            alt="dashboard"
                        />
                    </svelte:fragment>
                    <svelte:fragment slot="h2"
                        >什么是TorchV Bot？</svelte:fragment
                    >
                    <p class="mb-6 font-light text-gray-500 md:text-lg dark:text-gray-400">
                        TorchV Bot是一款基于大语言模型（Large Language Model，LLM）和检索增强生成（Retrieval-augmented generation，RAG）技术的问答机器人程序，可以帮助企业激活非结构化文档的价值。
                    </p>
                    <p class="mb-6 font-light text-gray-500 md:text-lg dark:text-gray-400">
                        本文我们详细讲述TorchV Bot的产品架构、功能和特性。
                    </p>
                    <a
                        href="/docs/whattorchvbot"
                        class="inline-flex items-center text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:focus:ring-primary-900"
                    >
                        进入查看
                        <ArrowRightSolid size="md" class="ml-2 -mr-1" />
                    </a>
                </Cta>
            </Section>
        </div>
    </div>
    <Footer />
</div>
