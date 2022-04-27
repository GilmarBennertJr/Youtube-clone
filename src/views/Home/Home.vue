<template>
    <div style="display: flex">
        <div class="sidebar">
            <sidebar></sidebar>
        </div>
        <div class="page">
            <navbar></navbar>
            
            <hr>

            <div class="tags">
                <tag v-for="(b, index) of badges" v-bind:key="index" v-bind:text="b.text" v-bind:actived="b.actived"></tag>
            </div>

            <hr>

            <div class="card-premium" v-show="!user">
                <div class="width50p">
                    <img src="../../assets/premium.png" alt="" style="width: 200px">
                    <h1 v-text="'YouTube sem anúncio para estudantes'">Outro texto</h1>
                    <btn type="primary" :full="false">Baixe Agora</btn>
                </div>
                <div class="width50p">
                    <img src="../../assets/pa1.png" alt="" style="width: 300px">
                </div>
            </div>

            <div class="videos">
                <banner v-for="(v, index) of videos" :key="index" :banner="v.banner" :bannerCanal="v.bannerCanal" :data="v.data" />
            </div>
            <button class="btn"></button>
        </div>
    </div>
</template>
<script>
import Navbar from '../../components/shared/navbar/Navbar.vue';
import Sidebar from '../../components/shared/sidebar/Siderbar.vue';
import Button from '../../components/shared/button/Button.vue';
import Banner from '../../components/shared/banner/Banner.vue';
import Tag from '../../components/shared/tag/Tag.vue'

import { tags, videos } from './mock.js'

export default {
    components: {
        'navbar': Navbar,
        'sidebar': Sidebar,
        'btn': Button,
        'banner': Banner,
        'tag': Tag
    },
    data() {
        return {
            user: undefined,
            badges: tags,
            videos: videos
        }
    }
}
</script>
<style>
    hr {
        border: 1px solid silver;
    }

    .sidebar {
        width: 15%;
    }

    .card-premium {
        padding: 20px; 
        display:flex
    }
    
    .page {
        width: 85%;
    }

    .videos {
        padding: 20px;
        display: flex;
        flex-wrap: wrap
    }

    .btn {
        color: olive !important;
    }

    .labelQualquer {
        color: green;
    }
</style>