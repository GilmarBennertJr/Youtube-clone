<template>
    <div class="navbar">
        <div class="search">
            <div class="search-component">
                <input type="text" placeholder="Pesquisar">
                <button>
                    <i class="fa fa-search"></i>
                </button>
            </div>
            <button class="microphone-button">
                <i class="fa fa-microphone"></i>
            </button>
        </div>
        <div class="icons">
            <btn type="primary" :full="false" icon="fa-user">Fazer Login</btn>
        </div>
    </div>
</template>
<script>
    import Button from '../../../components/shared/button/Button.vue';
    export default {
        components: {
            btn: Button
        }
    }
</script>
<style>
    .navbar {
        display: flex;
    }

    img {
        width: 100px;;
    }

    button {
        font-size: 20px;
        background: none;
        outline: none;
        border: none;
        padding: 0;
        margin: 0;
        font-size: 15px;
    }

    .logo {
        display: flex;
        width: 40%;
    }

    .search-component {
        display: flex;
        width: 100%;
    }

    input {
        width: 100%;
        border-radius: 3px 0px 0px 3px;
        border: 1px solid silver;
        height: 100%;
    }

    .search {
        margin-left: 20%;
        display: flex;
        width: 60%;
    }

    .search .search-component button {
        padding: 0px 10px 0px 10px;
        border: 1px solid black;
        border-radius: 0px 3px 3px 0px;
        border: 1px solid silver;
    }

    input {
        height: 38px;
    }

    .microphone-button {
        margin-left: 10px
    }

    .icons {
        width: 40%;
        text-align: right;
    }

    .icons button {
        border: 1px solid #0961d5;
        color: #0961d5;
        margin-right: 10px;
        padding: 5px;
        border-radius: 5px;
    }

    .icons i {
        margin-right: 10px;
        color: #0961d5
    }
</style>