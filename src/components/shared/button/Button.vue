<template>
    <button class="btn" :class="style">
        <i class="fas" :class="icon" v-if="icon"></i>
        <slot></slot>
    </button>
</template>
<script>

export default {
    props: ['icon', 'type', 'full'],
    computed: {
        style() {
            let style = this.type;
            if (this.full) {
                style += ' btn-full'
            }
            return style;
        }
    }
}
</script>

<style scoped>
    .btn {
        color: gray;
        border: 2px solid gray;
        border-radius: 5px;
        padding: 10px;
    }

    .btn {
        cursor: pointer;
    }

    .btn i {
        margin-right: 10px;
    }

    .btn-full {
        width: 100%;
    }

    .primary {
        color: #0961d5;
        border: 2px solid #0961d5;
    }

    .danger {
        color: #fe0000;
        border: 2px solid #fe0000;
    }

    .default-outline {
        background-color: white;
        color: black;
        border: 0px;
        width: 100%; 
        text-align: left
    }
</style>
