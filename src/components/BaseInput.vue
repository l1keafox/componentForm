<template>
  <label v-if="label" :for="uuid" >{{label}}</label>
  <input
    v-bind="$attrs"
    :placeholder="label"
    class="field"
    :value="modelValue"
    @input="$emit('update:modelValue',$event.target.value)"
    :id="uuid"
    :aria-describeby="error? `${uuid}-error` : null "
    :aria-invalid="error ? true : null "
  >
  <p
  v-if="error"
  class="errorMessage"
  :id="`${uuid}-error`"
  aria-live="assertive"
  >
  {{ error }}
  </p>
</template>
<script>
import UniqueID from '../features/UniqueID'
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: { // v-model prop
      type: [String, Number],
      default: ''
    },
    error: {
      type: String,
      deafult: ''
    }
  },
  setup () {
    const uuid = UniqueID().getID()
    return {
      uuid
    }
  }
}
</script>
