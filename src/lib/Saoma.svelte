<script>
    import { Modal,Button} from "flowbite-svelte";
    let defaultModal = false;
</script>


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