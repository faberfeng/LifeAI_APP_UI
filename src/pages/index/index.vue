<template>
  <view class="content">
    <main class="px-4 py-6 space-y-6">
      <!-- 欢迎区域 -->
      <section class="text-center py-4">
        <h1 class="hero-title text-2xl font-bold text-gray-800 mb-2" data-splitting>智能工作助手</h1>
        <p class="text-gray-600 text-sm">让AI助力您的日常工作</p>
      </section>
    </main>
    <!-- <image class="logo" src="/static/logo.png"></image>
    <view class="text-area">
      <text class="title">{{ title }}</text>
      <text>这是一个uni-app项目</text>
    </view> -->
    <Tabbar></Tabbar>
  </view>
</template>

<script setup >
import Tabbar from '../../components/Tabbar/index'
const title =ref('')
onShow(()=>{
  uni.hideTabBar({})
  title.value = import.meta.env.VITE_BASE_API
})
onLoad(()=>{
  console.log('页面加载')
  // 初始化文字分割动画
  try {
    Splitting()
  } catch (e) {
    // ignore
  }

  // 页面加载动画
  try {
    anime({
      targets: '[data-splitting] .char',
      translateY: [100, 0],
      opacity: [0, 1],
      easing: 'easeOutExpo',
      duration: 1000,
      delay: anime.stagger(30)
    })
  } catch (e) {}

  // 卡片进入动画
  try {
    anime({
      targets: '.card-hover',
      translateY: [50, 0],
      opacity: [0, 1],
      easing: 'easeOutExpo',
      duration: 800,
      delay: anime.stagger(100, { start: 300 })
    })
  } catch (e) {}
})
</script>

<style scoped lang="scss">
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
