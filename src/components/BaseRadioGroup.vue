<template>
  <component
    v-for="option in options"
    :key="option.value"
    :is="vertical ? 'div' : 'span'"
    :class = "{ horizontal: !vertical }"
  >
    <BaseRadio
      :label="option.label"
      :value="option.value"
      :name="name"
      :modelValue="modelValue"
      @update:modelValue="$emit('update:modelValue', $event)"
    />
  </component>
</template>

<script>
export default {
  props: {
    options: {
      type: Array,
      require: true
    },
    name: {
      type: String,
      required: true
    },
    modelValue: {
      type: [String, Number],
      required: true
    },
    vertical: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.horizontal {
  margin-right: 20px;
}
</style>
