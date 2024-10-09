<script setup lang="ts">
import axios from 'axios';
import { onMounted, ref } from 'vue';

const page = ref({
  pageNum: 1,
  pageSize: 10,
  page: [],
  total: 0,
});
const modal = ref<any>(null);

onMounted(async () => {
  const res = await axios.get('/api/student/page');
  console.log(res);
});
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
