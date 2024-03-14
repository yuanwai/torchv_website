<script>
    import { Navbar, Modal, NavBrand,NavLi,NavUl,NavHamburger,Button,MegaMenu, Dropdown, DropdownItem, DropdownDivider} from "flowbite-svelte";
    import { ChevronDownOutline} from "flowbite-svelte-icons";
    import Saoma from '$lib/Saoma.svelte'
    
    let menu2 = [
    { name: "TorchV Bot", help: "基于LLM和RAG的零维护对话机器人，快速让您的非结构化文件应用到企业业务中。" },
    { name: "TorchV Assistant", help: "（即将上线）快速处理海量文档，根据您需要的方式给出答案。" },
    ];
    let defaultModal = false;
</script>

<Navbar let:hidden let:toggle class="px-2 sm:px-4 py-2.5 fixed w-full z-20 top-0 start-0 border-b  border-slate-300">
    <NavBrand href="/">
      <img src="/images/logo_black.png"  class="me-3 h-6 sm:h-9" alt="TorchV Logo"/>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {hidden}>
      <NavLi class="cursor-pointer">
        产品<ChevronDownOutline class="w-3 h-3 ms-2 text-primary-800 dark:text-white inline"/>
      </NavLi>
      <MegaMenu full items={menu2} let:item>
        <a href="#" class="block p-3 rounded-lg hover:bg-gray-50 dark:hover:bg-gray-700 h-full">
          <div class="font-semibold dark:text-white">{item.name}</div>
          <span class="text-sm font-light text-gray-500 dark:text-gray-400">{item.help}</span>
        </a>
        <a slot="extra" href="/" class="block mt-4 p-4 text-left bg-local bg-gray-500 bg-center bg-no-repeat bg-cover rounded-lg bg-blend-multiply hover:bg-blend-soft-light dark:hover:bg-blend-darken">
          <p class="mb-5 max-w-xl text-sm p-0 font-extrabold tracking-tight leading-tight text-white">
            联系我们, 获得产品的试用权限.
          </p>
          <Button on:click={() => (defaultModal = true)} class="w-full">前往TorchV试用平台</Button>
        </a>
      </MegaMenu>
      <NavLi class="cursor-pointer" href="/pricing">
        价格
      </NavLi>
      <NavLi class="cursor-pointer" href="/docs">
        文档
      </NavLi>
      <NavLi class="cursor-pointer">
        公司<ChevronDownOutline class="w-3 h-3 ms-2 text-primary-800 dark:text-white inline" />
      </NavLi>
      <Dropdown class="w-44 z-20">
        <DropdownItem href="/company/team">关于我们</DropdownItem>
      </Dropdown>
    </NavUl>
  </Navbar>
  <Modal title="" bind:open={defaultModal} autoclose size="sm">
    <div class="flex justify-between mb-4 rounded-t sm:mb-5">
      <div class="text-lg text-gray-900 md:text-xl dark:text-white">
        <h3 class="font-semibold">您可以扫描下面的微信二维码进行咨询</h3>
      </div>
    </div>
    <!-- svelte-ignore a11y-missing-attribute -->
    <img src="/images/yuanwai.jpg"/>
    <div class="flex justify-between items-right">
      <Button color="red">
        关闭
      </Button>
    </div>
  </Modal>