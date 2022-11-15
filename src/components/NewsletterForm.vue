<template>

    <h1>Sign up for the newsletter!</h1>
    <form @submit="checkForm">

        <label for="name">Name: {{ name }}</label>
        <input v-model="name" type="text" id="name" name="name" placeholder="Your name..." required>


        <label for="surname">Surname: {{ surname }}</label>
        <input v-model="surname" type="text" id="surname" name="surname" placeholder="Your surname..." required>


        <label for="email">Email: {{ email }}</label>
        <p v-if="errors.length">Please type an email with an '@'</p>
        <input v-model="email" type="text" id="email" name="email" placeholder="Your email..." required>

        <label for="numberOfEmails">How many emails per week do you want to receive from us? </label>
        <select id="numberOfEmails" name="numberOfEmails">
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
        </select>
        <button type="submit" value="Submit">Submit</button>

    </form>
</template>

<script>
export default {
    name: 'NewsletterForm',
    data: function () {
        return {
            name: this.name,
            surname: this.surname,
            email: this.email,
            errors: [],
        }
    },
    methods: {
        checkForm: function (e) {
            this.errors = [];

            if (!this.name) {
                this.errors.push('Name required.');
            }
            if (!this.surname) {
                this.errors.push('Surname required.');
            }
            if (!this.email) {
                this.errors.push('Email required.');
            }
            if (!this.email.includes('@')) {
                this.errors.push('Email has to have @')
            } else {
                return true
            }

            e.preventDefault();
        }
    }
}
</script>

<style scoped>
form {
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
</style>