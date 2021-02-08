<template>
  <div>
    <form @submit.prevent>
      <div>
        <label for="name">お名前</label>
        <input id="name" v-model="form.name" type="text" />
      </div>
      <div>
        <label for="email">email</label>
        <input id="email" v-model="form.email" type="text" />
      </div>
    </form>
  </div>
</template>

<script lang="js">
import { defineComponent, reactive, watch } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const form = reactive({
      name: '',
      email: '',
    })

    watch(
      () => form.name,
      (currentName, prevName) => {
        console.info('currentName: ', currentName, 'prevName: ', prevName)
      },
      { deep: true},
    )

    return {
      form,
    }
  },
})
</script>
