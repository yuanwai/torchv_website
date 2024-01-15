<script lang="ts">
    import { Section, Contact } from "flowbite-svelte-blocks";
    import { Label, Input, Textarea, Button, MultiSelect, Badge } from "flowbite-svelte";
    import { EnvelopeSolid, MobilePhoneSolid } from "flowbite-svelte-icons";
    import Header from '$lib/Header.svelte';
    import Footer from '$lib/Footer.svelte';

  </script>
    
    <div class="flex flex-col space-y-2 pb-10">
      <div class="relative px-8">
        <Header/>
        <div style="height: 100%;" class="overflow-scroll pt-32">

    <Section name="contact">
      <Contact>
        <svelte:fragment slot="h2">获取试用账号</svelte:fragment>
        <svelte:fragment slot="paragraph">我们需要了解您的使用场景，再通过Email给您发送提供试用平台地址和账号！</svelte:fragment>
        <form class="space-y-8">
          <div>
            <Label for="email">Email</Label>
            <Input id="email" name="email" placeholder="name@domain" required>
              <EnvelopeSolid slot="left" size="sm" class="text-gray-500 dark:text-gray-400 ml-2" />
            </Input>
          </div>
          <div class="grid gap-6 mb-6 md:grid-cols-2">
            <div>
              <Label for="province">省份</Label>
              <Input id="province" name="province"  required />
            </div>
            <div>
              <Label for="city">城市</Label>
              <Input id="city" name="city"  required />
            </div>
            <div>
              <Label for="customer">如何称呼您</Label>
              <Input id="customer" name="customer" placeholder="例如：张先生/李小姐" required/>
            </div>
            <div>
              <Label for="phone">手机(选填)</Label>
              <Input id="phone" name="phone" placeholder="选填：手机号码">
                <MobilePhoneSolid slot="left" size="sm" class="text-gray-500 dark:text-gray-400 ml-2" />
              </Input>
            </div>
            <div>
              <Label for="company" class="block mb-2">所属公司</Label>
              <Input id="company" name="company" placeholder="请填写您所在公司名称" required />
            </div>
            <div>
              <Label for="industry" class="block mb-2">所在行业</Label>
              <Input id="industry" name="industry" placeholder="请填写您所在行业" required />
            </div>
          </div>
          <div>
            <Label for="usecase">使用场景</Label>
            <Textarea id="usecase" name="usecase" placeholder="请简要描述您的使用场景..." label="Your Use Case" />
          </div>
          <Button>提交申请</Button>
        </form>
      </Contact>
    </Section>
    <Footer/>
    </div>
    </div>
    </div>