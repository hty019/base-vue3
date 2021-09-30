<template>
  <h1>About {{ name }}</h1>
</template>

<script lang='ts'>
  import { computed } from 'vue'
  import { useStore } from 'vuex'

  const store = useStore()

  const name = computed(()=> {
    return store.state.user.name
  })
</script>

<style scoped>

</style>