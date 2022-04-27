<template>
    <span class="badge" :class="actived ? 'actived' : ''">{{ text }}</span>
</template>
<script>
    export default {
        props: ["text", 'actived']
    }
</script>
<style scoped>
    .badge {
        border: 1px solid silver;
        padding: 5px 10px 5px 10px;
        border-radius: 15px;
        font-size: 10px;
        margin: 2px;
        background-color: rgb(230, 230, 230);
    }

    .badge:hover {
        background-color: silver;
        color: black;
        cursor: pointer;
    }

    .actived {
        background-color: black;
        color: white;
    }
</style>