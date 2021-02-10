<template>
  <div>
    <label for="name">お名前</label>
    <!-- <input id="name" :value="value" @input="$emit('input', $event.target.value)" type="text" /> -->
    <input id="name" :value="value" type="text" @input="updateValue" />
  </div>
</template>

<script lang="js">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  props: {
    value: {
      type: String,
      required: true
    },
  },
  setup(_, {emit}) {
    const updateValue = (e) => {
      emit('input', e.target.value)
    }
    return {
      updateValue
    }
  },
})
</script>
