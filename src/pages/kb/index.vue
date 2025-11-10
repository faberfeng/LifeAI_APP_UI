<template>
  <view>
    <view class="kb-content">
      <view class="kb-item" v-for="item in kbList" :key="item.id">
        <view class="kb-item-title">{{ item.title }}</view>
        <view class="kb-item-content">{{ item.content }}</view>
      </view>
    </view>
    <Tabbar></Tabbar>
  </view>
</template>

<script setup>
import Tabbar from '../../components/Tabbar/index'
import { ref } from 'vue'

const kbList = ref([
  {
    id: 1,
    title: '知识库1',
    content: '这是知识库1的内容'
  },
  {
    id: 2,
    title: '知识库2',
    content: '这是知识库2的内容'
  }
])
</script>

<style scoped lang="scss">
.kb-content {
  padding: 20rpx;
}

.kb-item {
  margin-bottom: 20rpx;
}

.kb-item-title {
  font-size: 24rpx;
  font-weight: bold;
}

.kb-item-content {
  font-size: 20rpx;
}
</style>