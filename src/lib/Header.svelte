<script>
    import { Navbar, NavBrand,NavLi,NavUl,NavHamburger,Button,MegaMenu, Dropdown, DropdownItem, DropdownDivider} from "flowbite-svelte";
    import { ChevronDownOutline} from "flowbite-svelte-icons";

    let menu2 = [
    { name: "TorchV Bot", help: "基于LLM和RAG的零维护对话机器人." },
    { name: "TorchV Assistant", help: "快速处理海量文档，给您想要的总结答案." },

    { name: "产业招商数字名片", help: "赶快让您的招商人员拥有7x24的数字分身." },
    { name: "极速临展", help: "仅需一分钟，讲好文物背后的故事." },
    ];
</script>

<Navbar let:hidden let:toggle class="px-2 sm:px-4 py-2.5 fixed w-full z-20 top-0 start-0 border-b">
    <NavBrand href="/">
      <img src="/images/logo_black.png"  class="me-3 h-6 sm:h-9" alt="TorchV Logo"/>
    </NavBrand>
    <div class="flex md:order-2">
      <Button size="sm">登录</Button>
      <NavHamburger />
    </div>

    <NavHamburger on:click={toggle} />
    <NavUl {hidden}>
      <NavLi class="cursor-pointer">
        产品<ChevronDownOutline class="w-3 h-3 ms-2 text-primary-800 dark:text-white inline"/>
      </NavLi>
      <MegaMenu full items={menu2} let:item>
        <a href="/" class="block p-3 rounded-lg hover:bg-gray-50 dark:hover:bg-gray-700 h-full">
          <div class="font-semibold dark:text-white">{item.name}</div>
          <span class="text-sm font-light text-gray-500 dark:text-gray-400">{item.help}</span>
        </a>
        <a slot="extra" href="/try" class="block mt-4 p-4 text-left bg-local bg-gray-500 bg-center bg-no-repeat bg-cover rounded-lg bg-blend-multiply hover:bg-blend-soft-light dark:hover:bg-blend-darken">
          <p class="mb-5 max-w-xl text-sm p-0 font-extrabold tracking-tight leading-tight text-white">
            只需进行简单注册, 即可获得产品的试用权限.
          </p>
          <Button>前往TorchV试用平台</Button>
        </a>
      </MegaMenu>
      <NavLi class="cursor-pointer">
        文档中心<ChevronDownOutline class="w-3 h-3 ms-2 text-primary-800 dark:text-white inline" />
      </NavLi>
      <Dropdown class="w-44 z-20">
        <DropdownItem href="/">文档</DropdownItem>
        <DropdownItem href="/">客户案例</DropdownItem>
        <DropdownItem href="/">Blog</DropdownItem>
      </Dropdown>
      <NavLi class="cursor-pointer">
        公司<ChevronDownOutline class="w-3 h-3 ms-2 text-primary-800 dark:text-white inline" />
      </NavLi>
      <Dropdown class="w-44 z-20">
        <DropdownItem href="/">关于我们</DropdownItem>
        <DropdownItem href="/">合作伙伴</DropdownItem>
        <DropdownItem href="/">最近新闻</DropdownItem>
        <DropdownItem href="/">联系我们</DropdownItem>
      </Dropdown>
    </NavUl>
  </Navbar>