<template>
  <div v-if="firstPage">
    <NewsletterForm />
  </div>
  <div v-if="secondPage">
    <h1>Thank you for signing up for our newsletter. We'll be in touch!</h1>
    <img src="@/assets/kitty.png" />
  </div>
</template>

<script>
import NewsletterForm from './components/NewsletterForm.vue';

export default {
  name: 'App',
  components: {
    NewsletterForm
  },
  data: function () {
    return {
      firstPage: true,
      secondPage: false
    };
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
