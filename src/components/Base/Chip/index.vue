<script lang="ts" setup>
type Props = {
  // チップのスタイル
  variant: 'elevated' | 'flat' | 'outlined' | 'text' | 'plain'
  color?: string
  content?: string
  // Material Design Icons 参照
  icon?: string
  // アイコンの位置
  iconDirection?: 'left' | 'right'
  // サイズ
  size: 'small' | 'medium'
}

withDefaults(defineProps<Props>(), {
  variant: 'elevated',
  size: 'medium'
})
</script>

<template>
  <v-chip v-bind="$attrs" :variant="variant" :color="color" :class="`base-chip-${size}`">
    <v-icon
      v-if="iconDirection === 'left'"
      :style="size == 'small' ? 'font-size: 12px' : 'font-size: 16px'"
      class="base-chip-icon"
      :icon="icon"
    >
      {{ icon }}
    </v-icon>
    <span :style="size == 'small' ? 'font-size: 8px' : 'font-size: 12px'">
      {{ content }}
    </span>
    <v-icon
      v-if="iconDirection === 'right'"
      :style="size == 'small' ? 'font-size: 12px' : 'font-size: 16px'"
      class="base-chip-icon"
      :icon="icon"
    >
      {{ icon }}
    </v-icon>
  </v-chip>
</template>

<style lang="css" scoped>
.base-chip-small {
  padding: 4px;
}

.base-chip-medium {
  padding: 4px;
}

.base-chip-icon {
  margin: 4px;
}
</style>
