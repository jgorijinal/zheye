<template>
  <div class="row">
    <div v-for="column in columnList" :key="column.id" class="col-4 mb-4">
      <div class="card h-100 shadow-sm">
        <div class="card-body text-center">
          <img :src="column.avatar" class="rounded-circle border w-25 my-3 " :alt="column.title">
          <h5 class="card-title">{{column.title}}</h5>
          <p class="card-text">{{column.description}}</p>
          <a href="#" class="btn btn-outline-primary">进入专栏</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
export interface columnProps { // column 的类型
  id: number
  title: string
  avatar: string
  description: string
}
export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      type: Array as PropType<columnProps[]>,
      required: true
    }
  },
  setup (props) {
    // 处理没有 avatar 的 column
    const columnList = computed(() => {
      return props.list.map(column => {
        if (!column.avatar) {
          column.avatar = require('@/assets/column.jpg')
        }
        return column
      })
    })
    return { columnList }
  }
})
</script>

<style>

</style>
