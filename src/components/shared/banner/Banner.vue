<template>
    <div class="card-video" @mouseover="showVideo = true" @mouseleave="showVideo = false">
        <img :src="banner" alt="" class="width100p" v-if="!showVideo">
         <video class="width100p" autoplay autostart loop v-else>
            <source src="https://jsoncompare.org/LearningContainer/SampleFiles/Video/MP4/Sample-MP4-Video-File-for-Testing.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video> 
        <label v-if="showVideo" for="" style="position:absolute;top:10px; background-color:white;font-size:6px;padding:3px;border-radius: 5px">
            Mantenha o cursor em cima do vídeo para ver uma prévia
        </label>
        <div class="inline-flex">
            <div>
                <img class="banner-canal" :src="bannerCanal" alt="">
            </div>
            <div>
                <label class="nome-video">{{ data.name }}</label>
                <label class="nome-canal">{{ data.canal }}</label>
                <label class="total-visualizacao">{{ data.visualizacaoData }}</label>
            </div>
        </div>
        <div class="hover-icons" style="display: block; margin-top: 10px; display:none">
            <btn icon="fa-play">Assistir mais Tarde</btn>
            <btn icon="fa-list">Adicionar na Fila</btn>
        </div>
    </div>
</template>
<script>
    import Button from '../button/Button.vue';

    export default {
        components: {
            btn: Button
        },
        data () {
            return {
                showVideo: false
            }
        },
        props: ['banner', 'bannerCanal', 'data'],
        methods: {
            zoom() {
                this.bannerCanal += ' animated zoomIn'
            },
            playVideo() {
                this.showVideo = true;
            }
        }
    }
</script>
<style scoped>
    .banner-canal {
        border-radius: 50%; 
        width: 30px; 
        height: 30px
    }

    .card-video:hover {
        width: 300px;
        position:relative;
        border: 1px solid silver;
        border-radius: 5px;
        box-shadow: 5px 5px 5px silver;
    }

    .card-video:hover .hover-icons {
        display: inline-block !important;
    }

    .card-video {
        padding: 5px;
        flex: 1 0 auto; 
        width: 20%;
        margin-top: 10px
    }

    label {
        margin-left: 10px; 
        display: block;
    }

    .nome-video {
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
    }

    .nome-canal {
        font-size: 13px; 
        color: #909090;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 1;
        -webkit-box-orient: vertical;
    }

    .total-visualizacao {
        font-size: 10px; 
        color: #909090
    }

    .bounce-enter-active {
        animation: bounce-in 0.5s;
        }
        .bounce-leave-active {
        animation: bounce-in 0.5s reverse;
        }
        @keyframes bounce-in {
        0% {
            transform: scale(0);
        }
        50% {
            transform: scale(1.25);
        }
        100% {
            transform: scale(1);
        }
        }
</style>