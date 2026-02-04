<template>
  <div class="app">
    <Loader />
  </div>
</template>

<script>
import Loader from './components/Loader.vue'

export default {
  name: 'App',
  components: {
    Loader,
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgb(56, 53, 53);
}
</style>
