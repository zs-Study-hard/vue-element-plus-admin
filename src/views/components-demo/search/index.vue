<template>
  <div>
    <el-alert
      effect="dark"
      :closable="false"
      title="封装 Element 的 Form 组件，实现查询、重置等功能，并提供了三种布局风格。"
      type="info"
      style="margin-bottom: 20px"
    />
    <el-alert
      effect="dark"
      :closable="false"
      title="经典风格。"
      type="info"
      style="margin-top: 20px; margin-bottom: 20px"
    />
    <div class="searh">
      <com-search
        :schema="classicData"
        @search-submit="searchSubmit1"
        @reset-submit="resetSubmit1"
      />
      <div> 查询/重置后的数据：{{ formData1 }} </div>
    </div>

    <el-alert
      effect="dark"
      :closable="false"
      title="底部操作按钮风格。"
      type="info"
      style="margin-top: 20px; margin-bottom: 20px"
    />
    <div class="searh">
      <com-search
        layout="bottom"
        :schema="classicData"
        @search-submit="searchSubmit2"
        @reset-submit="resetSubmit2"
      />
      <div> 查询/重置后的数据：{{ formData2 }} </div>
    </div>

    <el-alert
      effect="dark"
      :closable="false"
      title="右侧操作按钮风格。"
      type="info"
      style="margin-top: 20px; margin-bottom: 20px"
    />
    <div class="searh">
      <com-search
        layout="right"
        :schema="classicData"
        @search-submit="searchSubmit3"
        @reset-submit="resetSubmit3"
      />
      <div> 查询/重置后的数据：{{ formData3 }} </div>
    </div>
  </div>
</template>

<script setup lang="ts" name="SearchDemo">
import { ref } from 'vue'
import { data as classicData } from './data'
const formData1 = ref<Nullable<IObj>>(null)
const formData2 = ref<Nullable<IObj>>(null)
const formData3 = ref<Nullable<IObj>>(null)

function searchSubmit1(data: any): void {
  formData1.value = data
}

function resetSubmit1(data: any): void {
  formData1.value = data
}

function searchSubmit2(data: any): void {
  formData2.value = data
}

function resetSubmit2(data: any): void {
  formData2.value = data
}

function searchSubmit3(data: any): void {
  formData3.value = data
}

function resetSubmit3(data: any): void {
  formData3.value = data
}
</script>

<style lang="less" scoped>
.searh {
  padding: 20px;
  background: #fff;
}
</style>
