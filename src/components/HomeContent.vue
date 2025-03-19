<script setup lang="ts">
import { ref } from "vue";
import { Button } from "@/components/ui/button";
import { Textarea } from "@/components/ui/textarea";
import { Input } from "@/components/ui/input";
import { Search } from "lucide-vue-next";
import { Rate } from "ant-design-vue";
import { Tabs } from "ant-design-vue";
import NavigationMenu from "@/components/home/NavigationMenu.vue";

const { TabPane } = Tabs;

// 定义响应式变量
const activeKey = ref("JavaScript");
</script>

<template>
  <div class="min-h-screen flex flex-col">
    <a-layout>
      <!-- Header -->
      <a-layout-header
        class="fixed top-0 left-0 right-0 z-50 bg-gray-100 shadow-md"
      >
        <div class="container mx-auto px-4 flex justify-between items-center">
          <div class="text-xl font-bold text-blue-600">NominaAI</div>
          <NavigationMenu></NavigationMenu>

          <div class="flex space-x-4">
            <div class="relative w-full max-w-sm items-center">
              <Input
                id="search"
                type="text"
                placeholder="Search..."
                class="pl-10"
              />
              <span
                class="absolute start-0 inset-y-0 flex items-center justify-center px-2"
              >
                <Search class="size-6 text-muted-foreground" />
              </span>
            </div>
            <div>
              <!-- <button>登录</button> -->
            </div>
          </div>
        </div>
      </a-layout-header>

      <!-- Hero Section -->
      <div class="bg-gradient-to-b from-blue-900 to-blue-800 text-white py-20">
        <div class="container mx-auto px-4">
          <section class="relative max-w-screen-xl mx-auto py-4 px-4 sm:px-8">
            <div
              class="absolute top-0 left-0 w-full h-full bg-white opacity-40"
            ></div>
            <div class="relative z-10 gap-5 items-center lg:flex">
              <div
                class="flex-1 max-w-lg py-5 sm:mx-auto sm:text-center lg:max-w-max lg:text-left"
              >
                <h3 class="text-3xl text-gray-800 font-semibold md:text-4xl">
                  build your websites with
                  <span class="text-indigo-600">high performance</span>
                </h3>
                <p class="text-gray-500 leading-relaxed mt-3">
                  Nam erat risus, sodales sit amet lobortis ut, finibus eget
                  metus. Cras aliquam ante ut tortor posuere feugiat. Duis
                  sodales nisi id porta lacinia.
                </p>
                <a
                  class="mt-5 px-4 py-2 text-indigo-600 font-medium bg-indigo-50 rounded-full inline-flex items-center"
                  href="javascript:void()"
                >
                  Try it out
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6 ml-1 duration-150"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      strokeLinecap="round"
                      strokeLinejoin="round"
                      strokeWidth="{2}"
                      d="M13 7l5 5m0 0l-5 5m5-5H6"
                    />
                  </svg>
                </a>
              </div>
              <div class="flex-1 mt-5 mx-auto sm:w-9/12 lg:mt-0 lg:w-auto">
                <img
                  src="https://i.postimg.cc/kgd4WhyS/container.png"
                  alt=""
                  class="w-full"
                />
              </div>
            </div>
          </section>
        </div>
      </div>

      <!-- Content -->
      <a-layout-content
        class="flex-grow container mx-auto p-4 overflow-y-auto bg-gray-50"
      >
        <!-- 示例代码部分 -->
        <div class="bg-white p-8 rounded-lg shadow-md mt-8">
          <a-tabs v-model:activeKey="activeKey">
            <a-tab-pane key="JavaScript" tab="JavaScript">
              <a-textarea
                placeholder="请输入您想要命名的变量、方法或文件的中文描述..."
                rows="4"
                class="w-full mb-4"
              />
              <a-button
                type="primary"
                class="bg-blue-600 hover:bg-blue-700 w-full"
              >
                一键生成命名建议
              </a-button>
            </a-tab-pane>
            <!-- 其他编程语言的 Tab Pane 可以类似添加 -->
          </a-tabs>
        </div>

        <!-- 推荐部分 -->
        <div class="mt-8">
          <h3 class="text-xl font-bold mb-4">热门推荐</h3>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
            <div class="bg-white p-4 rounded-lg shadow-md">
              <h4 class="text-lg font-semibold">getUserProfile</h4>
              <p class="text-gray-600">〈取用户信息的方法〉</p>
              <p class="text-sm text-gray-500">使用次数: 2345</p>
              <a-rate :value="4.9" disabled class="mt-2" />
            </div>
            <!-- 其他推荐项可以类似添加 -->
          </div>
        </div>
      </a-layout-content>

      <!-- Footer -->
      <a-layout-footer class="bg-gray-900 text-white py-6">
        <div class="container mx-auto px-4">
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            <div>
              <h4 class="font-bold mb-4">快速开始</h4>
              <ul class="space-y-2">
                <li><a href="#" class="hover:text-blue-400">基础教程</a></li>
                <li><a href="#" class="hover:text-blue-400">最佳实践</a></li>
                <li><a href="#" class="hover:text-blue-400">常见问题</a></li>
              </ul>
            </div>
            <div>
              <h4 class="font-bold mb-4">开发文档</h4>
              <ul class="space-y-2">
                <li><a href="#" class="hover:text-blue-400">API 文档</a></li>
                <li><a href="#" class="hover:text-blue-400">命名规范</a></li>
                <li><a href="#" class="hover:text-blue-400">示例代码</a></li>
              </ul>
            </div>
            <div>
              <h4 class="font-bold mb-4">关于我们</h4>
              <ul class="space-y-2">
                <li><a href="#" class="hover:text-blue-400">团队介绍</a></li>
                <li><a href="#" class="hover:text-blue-400">联系方式</a></li>
                <li><a href="#" class="hover:text-blue-400">加入我们</a></li>
              </ul>
            </div>
            <div>
              <h4 class="font-bold mb-4">更多资源</h4>
              <ul class="space-y-2">
                <li><a href="#" class="hover:text-blue-400">博客</a></li>
                <li><a href="#" class="hover:text-blue-400">社区</a></li>
                <li><a href="#" class="hover:text-blue-400">反馈建议</a></li>
              </ul>
            </div>
          </div>
          <div class="text-center mt-8">
            <p class="text-sm">© 2024 NominaAI. All rights reserved.</p>
          </div>
        </div>
      </a-layout-footer>
    </a-layout>
  </div>
</template>

<style scoped>
/* 添加一些自定义样式 */
.bg-gradient-to-b {
  background-image: linear-gradient(
    to bottom,
    #e0f7fa,
    /* 浅蓝色 */ #f3e5f5 /* 浅紫色 */
  ); /* 调整渐变颜色 */
}

.bg-gray-50 {
  background-color: #f9fafb; /* 内容区域背景色 */
}

.bg-gray-100 {
  background-color: #fff;
}

.bg-gray-900 {
  background-color: #f4f5f7; /* 页脚背景色 */
}
</style>
