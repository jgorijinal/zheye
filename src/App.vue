<template>
  <!--类名(bootstrap) : container-->
  <div class='container'>
    <ColumnList :list='testData'></ColumnList>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css' // 引入 bootstrap 样式表
import ColumnList, { columnProps } from './components/ColumnList.vue'

export default defineComponent({
  name: 'App',
  components: {
    ColumnList
  },
  setup () {
    const testData: columnProps[] = [
      {
        id: 1,
        title: 'test1的专栏',
        description:
          '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧, 这是的test1专栏，有一段非常有意思的简介，可以更新一下欧',
        avatar:
          'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_150,w_150'
      },
      {
        id: 2,
        title: 'test2的专栏',
        description: '这是的test2专栏，有一段非常有意思的简介，可以更新一下欧',
        avatar: ''
        // 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100'
      },
      {
        id: 3,
        title: 'test3的专栏',
        description:
          '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧 这是的test1专栏，有一段非常有意思的简介，可以更新一下欧',
        avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100'
      },
      {
        id: 4,
        title: 'test4的专栏',
        description: '这是的test2专栏，有一段非常有意思的简介，可以更新一下欧',
        avatar:
          'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100'
      }
    ]
    return { testData }
  }
})
</script>

<style></style>
