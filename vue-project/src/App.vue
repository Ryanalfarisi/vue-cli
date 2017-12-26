<template>
  <div id="app">
    <parent/>
  </div>
</template>

<script>
import parentComponents from './components/parentComponents'

export default {
  name: 'app',
  components: {
    'parent' : parentComponents
  }
}
</script>

<style>
</style>
