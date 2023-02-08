<template>
  <label>Title</label>
  <input
    v-bind="$attrs"
    :placeholder="label"
    class="field"
    :value="modelValue"
    @input="$emit('update:modelValue',$event.target.value)"
  >
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: { // v-model prop
      type: [String, Number],
      default: ''
    }
  }
}
</script>
