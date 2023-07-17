<script>
export default {
    data() {
        return {
            greeting: 'Hello World!'
        }
    },
    methods: {

    },
}
</script>

<template>
    <div class="my_loader">
    
        <img src="https://i.gifer.com/9Lwu.gif" alt="">
    </div>
</template>

<style lang="scss" scoped>
    .my_loader {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;

        img {
            width: 500px;
            border-radius: 10px;
        }
    }
</style>