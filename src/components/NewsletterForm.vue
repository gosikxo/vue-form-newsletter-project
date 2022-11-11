<template>
    <div class="form">
        <div class="formInput">
            <label for="name">Name </label>
            <input type="text" id="name" name="name" required>
        </div>
        <div class="formInput">
            <label for="name">Surname </label>
            <input type="text" id="surname" name="surname" required>
        </div>
        <div class="formInput">
            <label for="email">Email </label>
            <input type="text" id="email" name="email" required>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NewsletterForm'
}
</script>

<style scoped>
.form {
    display: flex;
    flex-direction: column;
}
</style>