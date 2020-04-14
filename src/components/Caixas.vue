<template>
    <div id="caixa">
        <h1>Caixas</h1>
        <div class="caixinhas" v-for="(caixa, index) in caixinhas" :key="index" :style="caixa.cor">
{{caixa.titulo}}
        </div>
    </div>
</template>

<script>


export default {
    name: "Caixas",
    computed: {
        caixinhas(){
           return this.$store.state.caixinhas
        } 
    }
}
</script>

<style>
    #caixa{
        width: 220px;
        height: 120px;
        border: 1px solid burlywood;
        margin: 30px auto 10px auto;
        display: flex;
        flex-wrap: wrap;
        border-radius: 5px;
        background: #C6FFDD;  /* fallback for old browsers */
        background: -webkit-linear-gradient(to right, #f7797d, #FBD786, #C6FFDD);  /* Chrome 10-25, Safari 5.1-6 */
        background: linear-gradient(to right, #f7797d, #FBD786, #C6FFDD); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    }
    .caixinhas{
        width: 50px;
        height: 50px;
        border: 1px solid burlywood;
        border-radius: 5px;
        margin: 5px auto 0 auto;
        text-align: center;
        line-height: 50px;
        user-select: none;
        cursor: pointer;
        font-size: 20px;
    }
    h1{
        margin: auto 60px auto 60px;
        color: black;
        font-family: cursive;
    }
</style>