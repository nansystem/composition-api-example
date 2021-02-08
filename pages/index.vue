<template>
  <div>
    <form @submit.prevent>
      <div>
        <label for="email">email</label>
        <input id="email" ref="emailInput" type="text" />
      </div>
    </form>
  </div>
</template>

<script lang="js">
import { defineComponent, onMounted, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const emailInput = ref(null);

    onMounted(()=>{
      // composition api以前は this.$refs.emailInputで取得していた
      console.info("mounted!!", emailInput.value)
      emailInput.value.focus()
    })
    console.info("before mount", emailInput.value)

    return {
      emailInput,
    }
  },
})
</script>
