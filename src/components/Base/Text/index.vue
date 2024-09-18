<script lang="ts" setup>
type Props = {
  content: string
  type: string
  color?: string
}

const props = withDefaults(defineProps<Props>(), {
  type: 'p'
})

var typography: String
switch (props.type) {
  case 'h1':
    typography = 'h1'
    break
  case 'h2':
    typography = 'h2'
    break
  case 'h3':
    typography = 'h3'
    break
  case 'h4':
    typography = 'h4'
    break
  case 'h5':
    typography = 'h5'
    break
  case 'h6':
    typography = 'h6'
    break
  default:
    typography = 'p'
}
</script>

<template>
  <div :class="`basetext-${typography}`">{{ content }}</div>
</template>

<style lang="css" scoped>
.basetext-h1 {
  font-size: 48px;
  font-weight: 400;
}

.basetext-h2 {
  font-size: 40px;
  font-weight: 400;
}

.basetext-h3 {
  font-size: 36px;
  font-weight: 400;
}

.basetext-h4 {
  font-size: 32px;
  font-weight: 400;
}

.basetext-h5 {
  font-size: 28px;
  font-weight: 400;
}

.basetext-h6 {
  font-size: 24px;
  font-weight: 400;
}

.basetext-p {
  font-size: 20px;
  font-weight: 400;
}
</style>
