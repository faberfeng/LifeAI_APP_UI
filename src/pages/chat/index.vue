<template>
  <view class="container">
      <uve-ai-chat ref="aiChatRef" 
       @send="handleSendMessage" @receive="handleReceiveMessage" />
  </view>
   <!-- <Tabbar></Tabbar> -->
</template>

<script setup lang="ts">
import { ref } from "vue"
// import Tabbar from '../../components/Tabbar/index'
import UveAiChat from '../../components/uve-ai-chat/index'

const aiChatRef = ref()

// 处理用户发送消息
const handleSendMessage = (message: string) => {
  console.log("用户发送消息:", message)
  // 这里可以调用实际的API
}

// 处理AI回复消息
const handleReceiveMessage = (message: string) => {
  console.log("AI回复消息:", message)
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.chat-wrapper {
  flex: 1;
  overflow: hidden;
}
</style>