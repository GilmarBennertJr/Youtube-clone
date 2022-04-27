<template>
    <div>
        <div class="logo">
            <button style="margin-right: 15px">
                <i class="fas fa-bars"></i>
            </button>
            <img src="../../../assets/logo.png" />
        </div>   
        <div class="menu">
            <div v-for="(m, index) of menu1" :key="index" class="opcao">
                <btn type="default-outline" :full="true" :icon="m.icon">{{ m.label }}</btn>
            </div>

            <hr>

            <div v-for="(m, index) of menu2" :key="index" class="opcao">
                <btn type="default-outline" :full="true" :icon="m.icon">{{ m.label }}</btn>
            </div>

            <hr>

            <div>
                <p>Faça login para curtir vídeos, comentar e se inscrever.</p>
                <btn type="primary" :full="true" icon="fa-user">Fazer Login</btn>
            </div>

            <hr>

            <div>
                <small>
                    <p class="about"> Sobre Imprensa Direitos autorais Entre em contato Criadores de conteúdo Publicidade Desenvolvedores
    Termos Privacidade Política e segurança Como funciona o YouTube Testar os novos recursos </p>
                </small>
            </div>

        </div>
    </div>
</template>
<script>
    import Button from '../../../components/shared/button/Button.vue';

    export default {
        components: {
            btn: Button
        },
        data() {
            return {
                menu1: [{
                    icon: 'fa-house',
                    label: 'Inicio'
                },
                {
                    icon: 'fa-globe',
                    label: 'Explorar'
                },
                {
                    icon: 'fa-list',
                    label: 'Inscrições'
                }],
                menu2: [{
                    icon: 'fa-book',
                    label: 'Biblioteca'
                },
                {
                    icon: 'fa-arrow-rotate-left',
                    label: 'Histórico'
                }],
                menu3: []
            }
        }
    }
    
</script>
<style scoped>
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
        padding-left: 10px;
    }

    .logo {
        display: flex;
        width: 40%;
    }

    .menu {
        margin-top: 30px
    }

    .opcao i {
        margin-right: 20px;
    }

    .opcao button {
        padding: 10px;
    }

    hr {
        color: silver;
    }

    .about {
        font-size: 10px;
    }

    .labelQualquer {
        color: blue
    }
</style>