<script lang="ts" setup>
type Props = {
  variant: 'elevated' | 'flat' | 'outlined' | 'text' | 'plain'
  color: string
  disable?: Boolean
  content: string
  type: 'button' | 'icon-button'
  icon?: string
  iconDirection?: 'left' | 'right'
  size: 'small' | 'medium'
}

withDefaults(defineProps<Props>(), {
  variant: 'elevated',
  color: 'primary',
  type: 'button',
  size: 'medium'
})

type Emits = {
  (e: 'click', value: MouseEvent): void
}

const emit = defineEmits<Emits>()

const onClick = (e: MouseEvent) => {
  emit('click', e)
}
</script>

<template>
  <v-btn
    v-if="type === 'button'"
    v-bind="$attrs"
    :variant="variant"
    :color="color"
    :disable="disable"
    :class="`base-button-${size}`"
    @click="onClick"
  >
    <span :style="size == 'small' ? 'font-size: 12px' : 'font-size: 16px'">
      {{ content }}
    </span>
  </v-btn>
  <v-btn
    v-if="type === 'icon-button'"
    v-bind="$attrs"
    :variant="variant"
    :color="color"
    :disable="disable"
    :class="`base-button-${size}`"
    @click="onClick"
  >
    <v-icon
      v-if="iconDirection === 'left'"
      :style="size == 'small' ? 'font-size: 16px' : 'font-size: 20px'"
      class="base-button-icon"
      :icon="icon"
    >
      {{ icon }}
    </v-icon>
    <span :style="size == 'small' ? 'font-size: 12px' : 'font-size: 16px'">
      {{ content }}
    </span>
    <v-icon
      v-if="iconDirection === 'right'"
      :style="size == 'small' ? 'font-size: 16px' : 'font-size: 20px'"
      class="base-button-icon"
      :icon="icon"
    >
      {{ icon }}
    </v-icon>
  </v-btn>
</template>

<style lang="css" scoped>
.base-button-small {
  padding: 8px;
  border-radius: 10px;
  height: 36px !important;
}

.base-button-medium {
  padding: 12px;
  border-radius: 10px;
  height: 48px !important;
}

.base-button-icon {
  margin: 4px;
}
</style>
