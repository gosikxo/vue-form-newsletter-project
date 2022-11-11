<template>
  <h1>Sign up for the newsletter!</h1>
  <NewsletterForm />
</template>

<script>
import NewsletterForm from './components/NewsletterForm.vue';

export default {
  name: 'App',
  components: {
    NewsletterForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
