<template>
    <footer>
        <router-link to="/about">about</router-link>
        <p>copyright &copy; 2021</p>
    </footer>
</template>

<script>

export default {
    name: 'Footer',
    props: {
    },
    components: {
    },
}
</script>

<style scoped>
footer {
    font-size: 10px;
    font-weight: 100;
    margin-top: 20px;
    text-align: center;
    color:rgb(76, 65, 73);
}
</style>