<template>
  <div id="app">
    <HeaderComponent/>
    <todo/>
  </div>
</template>

<script>
import todo from './components/todo'
import HeaderComponent from './components/header'

import bootstrap from './assets/shards.css'

export default {
  name: 'App',
  components: {
    todo,
    HeaderComponent
  }
}
</script>

<style>
.navbar {
  width: 100%;
}
</style>
