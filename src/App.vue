<template>
  <div class="firstPage" v-if="firstPage">
    <NewsletterForm />
    <button @click="submitForm" type="submit" value="Submit">Submit</button>
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
    }
  },
  methods: {
    submitForm () {
      console.log(this.firstPage, this.secondPage)
      this.firstPage = !this.firstPage
      this.secondPage = !this.secondPage
    }
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

.firstPage {
  background-color: rgb(234, 232, 232);
  border-radius: 5px;
  padding: 20px;
}

button {
  width: 100%;
  background-color: #50b7c4;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
