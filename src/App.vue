<template>
  <div id="app">
    <home></home>
    <k-form></k-form>
  </div>
</template>

<script>
import Home from '@/components/BusProvideParent'
import KForm from '@/components/KForm'

export default {
  name: 'App',
  components: {
    Home,
    KForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
