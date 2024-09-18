<script lang="ts" setup>
import Card from '@/components/Card/index.vue'
</script>

<template>
  <div class="chip-container">
    <Card title="タイトル" content="内容が入ります。" direction="top" type="simple" />
    <Card title="タイトル" content="内容が入ります。" direction="bottom" type="simple" />
    <Card
      title="タイトル"
      content="内容が入ります。"
      direction="top"
      type="chip-card"
      chip-content="チップ"
      chip-color="warning"
    />
    <Card
      title="タイトル"
      content="内容が入ります。"
      direction="bottom"
      type="chip-card"
      chip-content="チップ"
    />
  </div>
</template>

<style lang="css" scoped>
.chip-container {
  display: flex;
  padding: 32px;
  gap: 16px;
}
</style>
