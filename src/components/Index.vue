<!--
 * @Author: ahmr-bot ahmrcxy@gmail.com
 * @Date: 2022-11-24 12:54:06
 * @LastEditors: ahmr-bot ahmrcxy@gmail.com
 * @LastEditTime: 2022-11-24 16:18:07
 * @FilePath: \Friends\Friends\src\components\HelloWorld.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <v-app id="inspire">
    <!--appbar-->
    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Frp 内网穿透联盟</v-toolbar-title>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" expand-on-hover rail permanent>
      <List />
    </v-navigation-drawer>
    <!--appbarend-->
    <v-main>
      <v-container>

        <template v-for="n in 1" :key="n">
          <v-card text="Frp 内网穿透联盟">
            <v-card-text>About： 意旨在为了 Frp 行业能够协同发展，共同进步，我们创建了此联盟，以下是联盟成员名单（按照名称首字母排序）</v-card-text>
          <v-timeline density="compact" align="start">
            <v-timeline-item
              v-for="links in links"
              :key="links.id"
              size="x-small"
            >     <v-avatar height="125" :image="links.logo_url"></v-avatar> <div class="mb-4">
    
                <div class="font-weight-normal">
                  <strong>名称: {{ links.name }}</strong> <v-btn :href="links.url">前往</v-btn>
                </div>
                <div>介绍: {{ links.description }}</div>
              </div></v-timeline-item>
          </v-timeline>
          </v-card>
        </template>

      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import List from './list.vue'
import { ref } from 'vue'
import axios from 'axios'
const links = ref([])
axios({
  method:'get',
  url:'https://cdn.jsdelivr.net/gh/China-Frp-Union/Union-Chain-Page/public/list.json'
}).then((res)=>{
  console.log(res.data.links)
  links.value = res.data
})
</script>
<script>
export default {
  data: () => ({ drawer: 111 }),
}
</script>