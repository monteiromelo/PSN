<template>
    <div class="main">
        <div v-if="menuPrincipal">
            <div class="menu" v-if="menuShowed=='1'">
                <button @click="CriaProjeto"> 
                Criar Projeto
                </button>
                <button> 
                Carregar Projeto
                </button>
            </div>
            <div class="menu" v-if="menuShowed=='2'">
                Nome do projeto: 
                <input type="text" v-model="nomeProjeto" />
                <button @click="SalvaProjeto">
                    Salvar
                </button>
                <button @click="menuShowed='1'">
                    Voltar
                </button>
            </div>
        </div>
        <div v-else>
            <div class="cenas">
                Projeto: {{ projetoAtual.nome }}
                <div v-for="(value, index) in projetoAtual.cenas" :key="index">
                    Cena {{ index + 1 }}
                    <button>
                        Editar Cena
                    </button>
                </div>
            </div>
            <button @click="AdicionaCena">
                Adicionar Cena
            </button>


        </div>

        <!-- TAG PARA ADICIONAR IMAGEM -->
        <!-- <img :src="img"> -->
    </div>
</template>

<script>
export default {
    data(){
        return {
            // img: require(`@/assets/gaga.png`), // OBJ PARA ADICIONAR IMAGEM
            menuPrincipal: true,
            menuShowed: '1',
            nomeProjeto:'',
            projeto: {
                nome: '',
                cenas: [{
                    hotspots: [{
                        x:'',
                        y:'',
                        tamX: '',
                        tamY: '',
                        icone: '',
                        cenaDestino: ''
                    }]
                }]
            },
            projetoAtual: '',
        }
    },
    mounted() {
        this.projetoAtual = this.projeto;
    },
    methods:{
        CriaProjeto(){
            this.menuShowed = '2'
        },
        SalvaProjeto() {
            this.projetoAtual.nome = this.nomeProjeto
            this.menuPrincipal = false
        },
        AdicionaCena() {
            this.projetoAtual.cenas.push(this.projeto.cenas[0])
            this.projetoAtual.nome = "xablau"
        }
    }
}
</script>

<style lang="scss" scoped>

.main {
    width: 800px;
    height: 600px;

    .menu {
    background-color: blue;
    width: 800px;
    height: 600px;
}
}



</style>