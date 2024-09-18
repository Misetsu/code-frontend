<script lang="ts" setup>
import BaseButton from '@/components/Base/Button/index.vue'
</script>

<template>
  <div class="button-container">
    <BaseButton
      variant="flat"
      color="primary"
      content="ボタン"
      type="button"
      size="medium"
    ></BaseButton>
    <BaseButton
      variant="outlined"
      color="secondary"
      content="ボタン"
      type="button"
      size="small"
    ></BaseButton>
    <BaseButton
      variant="elevated"
      color="warning"
      content="ボタン"
      type="icon-button"
      icon="mdi-checkbox-marked-circle"
      icon-direction="left"
      size="medium"
    ></BaseButton>
    <BaseButton
      variant="text"
      color="error"
      content="ボタン"
      type="icon-button"
      icon="mdi-checkbox-marked-circle"
      icon-direction="right"
      size="medium"
    ></BaseButton>
  </div>
</template>

<style lang="css" scoped>
.button-container {
  display: flex;
  padding: 32px;
  gap: 16px;
  align-items: center;
}
</style>
