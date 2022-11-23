<template>
  <div class="firstPage" v-if="currentPage == 'sign-up'">
    <h1>Sign up for the newsletter!</h1>
    <form @submit="this.submitForm">

      <label for="name">Name: {{ name }}</label>
      <input :style="[!this.missingName ? { 'border': '1px solid #ccc' } : { 'border': '1px solid red' }]"
        v-model="name" type="text" id="name" name="name" placeholder="Your name..." required>

      <label for="surname">Surname: {{ surname }}</label>
      <input :style="[!this.missingSurname ? { 'border': '1px solid #ccc' } : { 'border': '1px solid red' }]"
        v-model="surname" type="text" id="surname" name="surname" placeholder="Your surname..." required>

      <label for="email">Email: {{ email }}</label>
      <input :style="[!this.missingEmail ? { 'border': '1px solid #ccc' } : { 'border': '1px solid red' }]"
        v-model="email" type="text" id="email" name="email" placeholder="Your email..." required>

      <label for="numberOfEmails">How many emails per week do you want to receive from us? </label>
      <select id="numberOfEmails" name="numberOfEmails">
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
      </select>

    </form>
    <button @click.prevent="submitForm" type="submit" value="Submit">Submit</button>
    <div v-if="this.errors.length">
      <b>Please correct the following error(s):</b>
      <ul>
        <li v-for="(error, index) in this.errors" v-bind:key="index">
          {{ error }}
        </li>
      </ul>
    </div>
  </div>
  <div v-if="currentPage == 'success'">
    <h1>{{ this.name }}, thank you for signing up for our newsletter. We'll be in touch!</h1>
    <img src="@/assets/kitty.png" />
  </div>
</template>

<script>


export default {
  name: 'App',

  data: function () {
    return {
      currentPage: 'sign-up',
      name: this.name,
      surname: this.surname,
      email: this.email,
      errors: [],
      missingName: false,
      missingSurname: false,
      missingEmail: false
    }
  },

  methods: {
    checkForm: function () {

      this.errors = [];
      if (!this.name) {
        this.errors.push('Name required.')
        this.missingName = true
      }
      if (!this.surname) {
        this.errors.push('Surname required.')
        this.missingSurname = true
      }
      if (!this.email) {
        this.errors.push('Email required.')
        this.missingEmail = true
      }
      if (!this.email.includes('@')) {
        this.errors.push('Email has to have @')
      }
      return this.errors.length === 0


    },
    submitForm () {
      console.log(this.errors)
      if (this.checkForm()) {
        this.currentPage = "success"
      }
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

input[type=text],
select {
  width: 100%;
  padding: 10px 10px;
  margin: 8px;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}


select {
  width: 12%;
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

li {
  text-align: left;
}
</style>
