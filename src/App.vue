<template>
  <div id="app">
    <div class="container">
      <movies-app></movies-app>
    </div>
  </div>
</template>

<script>
import MoviesApp from './components/MoviesApp'

export default {
  name: 'App',
  components: { MoviesApp }
}
</script>
