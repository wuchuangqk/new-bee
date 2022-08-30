<template>
  <div class="tab-wrap">
    <div v-for="item in items" :key="item.value" class="tab-item" :class="{ active: item.value === active }"
      @click="click(item.value)">{{ item.label }}</div>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'
interface IItem {
  label: string
  value: number
}
const props = withDefaults(defineProps<{
  items: IItem[],
  modelValue: number
}>(), {
  items: () => [] as IItem[]
})
const call = defineEmits(['update:modelValue'])
const active = ref(props.modelValue)
const click = (value: number) => {
  active.value = value
  call('update:modelValue', value)
}
</script>

<style lang="scss" scoped>
.tab-wrap {
  display: flex;

  .tab-item {
    flex: 1;
    padding: 10px 0;
    text-align: center;

    &.active {
      color: red;
    }
  }
}
</style>