<template>
    <form>

        <label for="name">Name </label>
        <input type="text" id="name" name="name" placeholder="Your name..." required>


        <label for="surname">Surname </label>
        <input type="text" id="surname" name="surname" placeholder="Your surname..." required>


        <label for="email">Email </label>
        <input type="text" id="email" name="email" placeholder="Your email..." required>

        <label for="numberOfEmails">How many emails per week do you want to receive from us? </label>
        <select id="numberOfEmails" name="numberOfEmails">
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
        </select>

        <input type="submit" value="Submit">

    </form>
</template>

<script>
export default {
    name: 'NewsletterForm'
}
</script>

<style scoped>
form {
    background-color: rgb(234, 232, 232);
    border-radius: 5px;
    padding: 20px;
}

input[type=text], select {
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

input[type=submit] {
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