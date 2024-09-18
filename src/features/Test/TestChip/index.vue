<script lang="ts" setup>
import BaseChip from '@/components/Base/Chip/index.vue'
</script>

<template>
  <div class="chip-container">
    <BaseChip variant="elevated" color="primary" content="チップ" size="medium" />
    <BaseChip variant="flat" color="secondary" content="チップ" size="medium" />
    <BaseChip variant="outlined" color="error" content="チップ" size="small" />
  </div>
</template>

<style lang="css" scoped>
.chip-container {
  display: flex;
  padding: 32px;
  gap: 16px;
}
</style>
