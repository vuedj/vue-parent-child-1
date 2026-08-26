<template>
    <div class="container">
        <router-link :to="{ name: 'Home' }">Home</router-link> |
        <router-link :to="{ name: 'About' }">About</router-link>
        <div class="view">
            <router-view />
            <div></div>
        </div>
        <div class="footer">
            <strong
                >Note: This is a scenario where the parent component resets the
                input field in the child component.</strong
            >
        </div>
    </div>
</template>

<style scoped>
.container {
    max-width: 1440px;
    margin: 0 auto;
}
.view {
    margin-top: 20px;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}
.footer {
    margin-top: 20px;
    text-align: center;
    color: red;
    padding: 10px;
    background-color: #f1f1f1;
    border-top: 1px solid #ccc;
}
</style>
