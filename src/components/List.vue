<script setup lang="ts">
import { ref } from 'vue';

const modal = ref<any>(null);
</script>

<template>
  <div :style="{ width: '800px' }">
    <div>
      <a-button type="primary" @click="modal = { }">新增</a-button>
    </div>
    <div>
      <a-table />
    </div>
  </div>
  <a-modal
    :title="modal?.uid ? '编辑项目' : '新增项目'"
    v-model:open="modal">
  </a-modal>
</template>
