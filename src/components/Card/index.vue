<script lang="ts" setup>
import BaseChip from '@/components/Base/Chip/index.vue'
import BaseText from '@/components/Base/Text/index.vue'

type Props = {
  title: string
  content: string
  direction: 'top' | 'bottom'
  type: 'simple' | 'chip-card'
  chipContent?: string
  chipColor?: string
}

withDefaults(defineProps<Props>(), {
  type: 'simple',
  direction: 'top',
  chipColor: 'primary'
})
</script>

<template>
  <v-sheet elevated="2" class="card-container">
    <div v-if="direction == 'top'" class="title-row">
      <BaseText :content="title" type="h6"></BaseText>
      <BaseChip
        v-if="type == 'chip-card'"
        variant="flat"
        :content="chipContent"
        :color="chipColor"
        size="medium"
      />
    </div>
    <div class="content-row">
      <BaseText :content="content" type="p"></BaseText>
      <BaseChip
        v-if="direction == 'bottom' && type == 'chip-card'"
        variant="flat"
        :content="chipContent"
        :color="chipColor"
        size="medium"
      />
    </div>
    <div v-if="direction == 'bottom'" class="title-row">
      <BaseText :content="title" type="h6"></BaseText>
    </div>
  </v-sheet>
</template>

<style lang="css" scoped>
.card-container {
  border: 1px solid darkgray;
  border-radius: 16px;
  padding: 24px;
}

.title-row {
  display: flex;
  flex-direction: row;
  gap: 16px;
}

.content-row {
  display: flex;
  flex-direction: row;
  gap: 16px;
}
</style>
