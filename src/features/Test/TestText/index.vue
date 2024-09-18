<script lang="ts" setup>
import BaseText from '@/components/Base/Text/index.vue'
</script>

<template>
  <div class="text-container">
    <BaseText content="Heading1" type="h1" />
    <BaseText content="Heading2" type="h2" />
    <BaseText content="Heading3" type="h3" />
    <BaseText content="Heading4" type="h4" />
    <BaseText content="Heading5" type="h5" />
    <BaseText content="Heading6" type="h6" />
    <BaseText content="body" type="p" />
  </div>
</template>

<style lang="css" scoped>
.text-container {
  display: flex;
  padding: 32px;
  gap: 16px;
  align-content: center;
}
</style>
