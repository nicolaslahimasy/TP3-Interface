<template>
  <div>
    <BaseHeader />
    <HomePage />
    <BaseFooter />
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue'
import BaseHeader from './components/BaseHeader.vue'
import BaseFooter from './components/BaseFooter.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    BaseHeader,
    BaseFooter
  }
}
</script>