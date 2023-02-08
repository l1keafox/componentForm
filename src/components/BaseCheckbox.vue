<template>
  <input
    type="checkbox"
    :value="modelValue"
    class="field"
    @change="$emit('update:modelValue',$event.target.checked)"
  />
<label v-if="label">{{ label }}</label>
</template>

<script>
// Checkbox state into checked value
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped></style>
