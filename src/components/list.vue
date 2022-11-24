<!--
 * @Author: ahmr-bot ahmrcxy@gmail.com
 * @Date: 2022-11-24 14:37:22
 * @LastEditors: ahmr-bot ahmrcxy@gmail.com
 * @LastEditTime: 2022-11-24 14:40:31
 * @FilePath: \Friends\Friends\src\components\list.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
    <v-list>
      <v-list-item :prepend-avatar=avatar>
        <v-list-item-tittle>Frp 内网穿透联盟</v-list-item-tittle>
      </v-list-item>
    </v-list>
    <v-list>
      <v-list-item prepend-icon="home" title="首页"></v-list-item>
    </v-list>
    <v-divider></v-divider>
</template>
<script setup>
const avatar = './favicon.ico'
console.log(avatar)
</script>