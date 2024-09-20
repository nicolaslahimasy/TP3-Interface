<template>
  <div>
    <base-header />
    <HomePage />
    <base-footer />
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue'

export default {
  name: 'App',
  components: {
    HomePage
  }
}
</script>