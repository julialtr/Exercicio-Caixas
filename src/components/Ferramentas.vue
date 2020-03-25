<template>
  <div id="ferramentas">
<select v-model="caixaSel">
    <option value="" selected disabled>Selecione uma caixa</option>
    <option v-for="(caixa, index) in caixinhas" :key="index" :value="index">
        {{caixa.titulo}}
    </option>
</select>

<div id="paleta">
  <div class="cor" :style="cor" v-for="(cor, index) in cores" :key="index" @click="alteraCor(cor)"></div>
  <input id="caixaSelecao" v-model="titulo" type="text" placeholder="Digite o nome da caixa">
<button id="botao" @click="alterarTexto">OK</button>

</div>



  </div>
</template>

<script>
export default {
name: "Ferramentas",
props: ['caixinhas'],
data: function(){
    return{
        cores: ['background: brown', 'background: gray', 'background: green' ],
        caixaSel: '',
        titulo: ''
    }
}, methods: {
alteraCor: function(cor) {
   this.$emit('alteraCor', {
     cor: cor,
     caixa: this.caixaSel
   })
}, alterarTexto: function(){
  this.$emit('alterouTexto',{
    caixa: this.caixaSel,
    titulo: this.titulo
  })
}
}}
</script>

<style>
  #ferramentas{
    width: 330px;
    height: 180px;
    border: 1px solid burlywood;
    margin: 5px auto 5px auto;
    border-radius: 5px;
     background: #C6FFDD;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #f7797d, #FBD786, #C6FFDD);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #f7797d, #FBD786, #C6FFDD); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    text-align: center;
  }
  #ferramentas select{
    width: 260px;
    margin: 15px auto 15px auto;
    height: 30px;
    font-family: cursive;
    user-select: none;
    cursor: pointer;
  }
#paleta{
    width: 380px;
    height: 130px;
    display: flex;
    flex-wrap: wrap;
    margin-left: 36px;
}
.cor{
  width: 60px;
    height: 60px;
    border: 1px solid burlywood;
    margin-right: 3px;
}
#caixaSelecao{
width: 190px;
height: 30px;
font-family: cursive;
text-align: center;
user-select: none;

}
#botao{
width: 60px;
height: 36px;
margin-left: 10px;
font-family: cursive;
cursor: pointer;
}
</style> 