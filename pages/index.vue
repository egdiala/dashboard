<template>
  <Main class="space-y-8">
    <section>
      <div class="container mx-auto lg:px-8 px-4">
        <div class="flex lg:flex-row lg:space-x-4 flex-col space-y-4 justify-between lg:items-start">
          <div class="flex-col space-y-1 lg:grow">
            <h1 class="text-gray-900 font-medium lg:text-3xl text-2xl">Welcome back, Olivia</h1>
            <p class="text-gray-500 font-normal text-base">Track, manage and forecast your customers and orders.</p>
          </div>
          <div class="flex space-x-3">
            <Button icon="upload-cloud" label="Import" outlined/>
            <Button icon="plus" label="Add" regular/>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="container mx-auto lg:px-8 px-4">
        <div class="grid lg:grid-cols-3 grid-rows-3 gap-6">
          <div v-for="n in 3" :key="n" class="border border-[#EAECF0] shadow rounded-lg p-6 space-y-6">
            <div class="flex items-center space-x-2">
              <h5 class="text-gray-900 font-medium text-base grow">Total customers</h5>
              <Icon icon="more-vertical" class="text-gray-500"></Icon>
            </div>
            <div class="flex space-x-4 items-center">
              <div class="flex-col space-y-4 grow">
                <h3 class="text-gray-900 font-semibold lg:text-4xl text-3xl">2,420</h3>
                <div class="flex space-x-2 items-center">
                  <div class="flex space-x-1 items-center"><Icon icon="arrow-up" class="text-green-400"></Icon> <span class="text-green-700 font-medium text-sm">40%</span></div>
                  <span class="text-gray-500 font-medium text-sm">vs last month</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

  </Main>
</template>

<script>
import Main from "../components/Main.vue";
import Button from "../components/Button.vue";
export default {
    name: "IndexPage",
    components: { Main, Button }
}
</script>
