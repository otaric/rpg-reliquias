<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
const props = defineProps<{
  count: number
  atributo: string
}>()

const emit = defineEmits<{
  (e: 'plus'): void
  (e: 'minus'): void
}>()

function plus() {
  emit('plus')
}

function minus() {
  emit('minus')
}

function bonusNumber(n: number) {
  const bonus =
    (n - 10) / 2 < 0 && !Number.isInteger((n - 10) / 2)
      ? (n - 10) / 2 - 0.5
      : Math.trunc((n - 10) / 2)

  return bonus
}
</script>

<template>
  <tr border="~ light-800 opacity-50">
    <td text="xl uppercase center light-800" font="mono bold">
      <span>
        {{ props.atributo }}
      </span>
    </td>
    <td flex="~" border="x light-800 opacity-50">
      <button
        p="x-4"
        font="mono"
        text="lg uppercase light-800"
        outline="!none"
        hover:bg="light-800 opacity-20"
        @click="minus"
      >
        -
      </button>
      <span p="4" font="mono" text="lg center uppercase light-800" w=" 20">{{
        props.count
      }}</span>
      <button
        p="x-4"
        font="mono"
        text="lg uppercase light-800"
        outline="!none"
        hover:bg="light-800 opacity-20"
        @click="plus"
      >
        +
      </button>
    </td>
    <td font="mono" text="lg uppercase center light-800">
      <span>{{ bonusNumber(props.count) }}</span>
    </td>
  </tr>
</template>
