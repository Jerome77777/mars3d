<template>
  <mars-dialog :visible="true" right="10" top="10" >

    <a-form  :labelCol="{ span:4 }">
      <a-form-item label="分析值:">
        <mars-slider v-model:value="delta" :min="1" :max="100" :step="1" /></a-form-item>
      </a-form>
      <a-form-item label="">
        <a-space>
          <mars-button @click="drawRectangle">绘制区域</mars-button>
        </a-space>
      </a-form-item>
  </mars-dialog>
</template>

<script setup lang="ts">
import { ref } from "vue"
import * as mapWork from "./map.js"

const delta = ref(50)

// 绘制线
const drawRectangle = () => {
  mapWork.drawRectangle(delta.value)
}

</script>

<style scoped lang="less">
:deep(.ant-slider) {
  width: 240px;
}
</style>
