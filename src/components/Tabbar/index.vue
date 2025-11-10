<template>
  <view>
    <up-tabbar
      :value="store.activeTab"
      :fixed="true"
      :placeholder="true"
      :safeAreaInsetBottom="true"
    >
      <up-tabbar-item v-for="(item,index) in tabbarItems" :key="index" :icon="getTabbarIcon(item, index)" :text="item.text" @click="handleTabbarItemClick(item, index)"></up-tabbar-item>
    </up-tabbar>
  </view>
</template>

<script setup>
import {useAppStore} from "../../store";
const store = useAppStore()

const getTabbarIcon = (item, index) => {
  return store.activeTab === index ? item.selectedIcon : item.icon
}
const handleTabbarItemClick = (item,index)=>{
  console.log(store)
  store.activeTab=index
  const path = '/'+item.pagePath
  console.log(path,'ssssssssss')
  uni.switchTab({
    url: path
  })

}

const tabbarItems = [
  {
    "pagePath": "pages/index/index",
    // "iconPath": "static/logo.png",
    // "selectedIconPath": "static/logo.png",
    "icon": "home",
    "selectedIcon": "home-fill",
    "text": "首页"
  },
  {
    "pagePath": "pages/chat/index",
    // "iconPath": "static/logo.png",
    // "selectedIconPath": "static/logo.png",
    "icon": "chat",
    "selectedIcon": "chat-fill",
    "text": "Ai对话"
  },
   {
    "pagePath": "pages/kb/index",
    // "iconPath": "static/logo.png",
    // "selectedIconPath": "static/logo.png",
    "icon": "file-text",
    "selectedIcon": "file-text-fill",
    "text": "知识库"
  },
  {
    "pagePath": "pages/mine/index",
    "icon": "account",
    "selectedIcon": "account-fill",
    "text": "我的"
  }
  ]
</script>

<style scoped>

</style>