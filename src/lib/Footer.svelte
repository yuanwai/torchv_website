<script>
    import { Footer, FooterBrand, FooterCopyright, FooterIcon, FooterLink, FooterLinkGroup, Hr  } from "flowbite-svelte";
    import { GithubSolid, XCompanySolid} from "flowbite-svelte-icons";
</script>

<Hr/>

<Footer footerType="socialmedia">
    <div class="md:flex md:justify-between">
      <div class="mb-6 md:mb-0">
        <FooterBrand
          href="https://www.torchv.com"
          src="/images/logo_black.png"
          alt="Flowbite Logo"
        />
      </div>
      <div class="grid grid-cols-3 gap-8 sm:gap-6 sm:grid-cols-5">
        <div>
          <h2 class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white">
            产品
          </h2>
          <FooterLinkGroup>
            <FooterLink liClass="mb-4" href="/"> Bot</FooterLink>
          </FooterLinkGroup>
        </div>
        <div>
          <h2 class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white">
            文档中心
          </h2>
          <FooterLinkGroup>
            <FooterLink liClass="mb-4" href="/docs/manual">快速上手</FooterLink>
            <FooterLink liClass="mb-4" href="/docs/dev">API文档</FooterLink>
            <FooterLink liClass="mb-4" href="/docs/whattorchvbot">TorchV Bot简介</FooterLink>
          </FooterLinkGroup>
        </div>
        <div>
          <h2 class="mb-6 text-sm font-semibold uppercase text-gray-900 dark:text-white">
            联系我们
          </h2>
          <FooterLinkGroup>
            <FooterLink liClass="mb-4" href="/company/team">关于我们</FooterLink>
          </FooterLinkGroup>
        </div>
      </div>
    </div>
    <hr
      class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8"
    />
    <div class="sm:flex sm:items-center sm:justify-between">
      <FooterCopyright
        href="/"
        by="杭州萌嘉网络科技有限公司"
        copyrightMessage="版权所有"
      />
      <a class="text-sm text-gray-500" href="https://beian.miit.gov.cn/"
        >浙ICP备2023015070号-5</a
      >
      <div
        class="flex mt-4 space-x-6 rtl:space-x-reverse sm:justify-center sm:mt-0"
      >
        <FooterIcon href="https://www.x.com/torch_v">
          <XCompanySolid
            class="w-4 h-4 text-gray-500 dark:text-gray-500 hover:text-gray-900 dark:hover:text-white"
          />
        </FooterIcon>
        <FooterIcon href="/">
          <GithubSolid
            class="w-4 h-4 text-gray-500 dark:text-gray-500 hover:text-gray-900 dark:hover:text-white"
          />
        </FooterIcon>
      </div>
    </div>
  </Footer>