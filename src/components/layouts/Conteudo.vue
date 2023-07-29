<template>
    <div>
        <h1>{{ titulo }}</h1>
        <button @click="atualizarComponent()">Atualizar</button>
        <button @click="conteudo = 'home'">Home</button>
        <button @click="conteudo = 'publica-vaga'">Publicar Vaga</button>
        <component :is="conteudo"/>
        <!-- <home></home>
        <publica-vaga></publica-vaga> -->
    </div>
</template>
<script>
import Home from '../views/Home.vue'
import PublicaVaga from '../views/PublicaVaga.vue'
export default {
    name: 'Conteudo',
    components: {
        Home,
        PublicaVaga
    },
    data:()=>({
        teste: 'O component foi criado',
        titulo: 'Componente Conteudo',
        conteudo: ''
    }),
    methods: {
        atualizarComponent() {
            this.titulo += '#'
        }
    },
    beforeCreate() {
        console.log('Antes de criar', this.teste)
    },
    created(){
        console.log('Criado', this.teste)
    },
    beforeMount() {
        console.log('Antes de montar')
    },
    mounted() {
        console.log('Montado')
    },
    beforeUpdate() {
        console.log('Antes de atualizar')
    },
    updated() {
        console.log('Atualizado')
    },
    unmounted() {
        console.log('Antes de desmontar/destruir')
    },
    errorCaptured(){
        console.log('Error capturado')
    },
    renderTracked() {
        console.log('Re-renderização rastreada')
    },
    renderTriggered() {
        console.log('Re-renderização acionada')
    },
    activated() {
        console.log('Componente é ativado')
    },
    deactivated() {
        console.log('Componente é desativado')
    }
}
</script>