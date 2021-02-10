<template>
  <div>
    form: {{ form }}
    <form @submit.prevent>
      <InputName v-model="form.name" />
      <!-- <InputName :value="form.name" @input="form.name = $event" /> -->
    </form>
  </div>
</template>

<script lang="js">
import { defineComponent, reactive } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const form = reactive({
      name: '山田',
    })

    return {
      form
    }
  },
})
</script>
