<template>
  <p>HomePi</p>

  <p>Name in store is: {{ name }} </p>

  <input v-model='newName'/>

  <button @click='saveName'>Submit</button>
</template>

<script setup>
  import { useStore } from 'vuex'
  import { computed, ref } from 'vue'
  const store = useStore()
  import { useRouter } from 'vue-router'
  const router = useRouter()

  const name = computed(()=> {
    return store.state.user.name
  })

  const newName = ref('')
  function saveName() {
    store.dispatch('saveName',newName.value)
    newName.value =''
    router.push('/about')
  }
</script>

<style scoped>

</style>