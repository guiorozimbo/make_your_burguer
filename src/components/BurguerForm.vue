<template>
<div>
  <p>
    test
  </p>
  <div>
    <form action="" id="burguer-form">
      <div class="input-container">
        <label for="nome">Nome do Cliente:</label>
        <input type="text" id="nome" name="name" v-model="nome" placeholder="Digite o seu nome">
      </div>
      <div class="input-container">
        <label for="pao">Escolha o pão:</label>
        <select name="pao" id="pao" v-model="pao">
          <option value="margherita">Margherita</option>
          <option value="calabrese">Calabrese</option>
          <option value="portuguesa">Portuguesa</option>
          <option value="bacon">Bacon</option>
          <option value="pepperoni">Pepperoni</option>
          <option value="mushroom">Mushroom</option>
        </select>
      </div>

      <div class="input-container">
        <label for="pao">Escolha a carne:</label>
        <select name="pao" id="pao" v-model="pao">
          <option value="acem">Ácem</option>
          <option value="linguica">Linguiça</option>
          <option value="maminha">Maminha</option>
          <option value="patinho">Patinho</option>
          <option value="bacon">Bacon</option>
        </select>
      </div>

      <div id="opcionais-container" class="input-container">
        <label id="opcionais-title" for="opicionais">Selecione os opcionais:</label>
        <div class="checkbox-container">
          <input type="checkbox" id="quantidade" name="opicionais" v-model="opcionais" value="salame">
         <span>
          salame
         </span>
         <input type="checkbox" id="quantidade" name="opicionais" v-model="opcionais" value="salame">
         <span>
          salame
         </span>
         <input type="checkbox" id="quantidade" name="opicionais" v-model="opcionais" value="salame">
         <span>
          salame
         </span>
        </div>
      </div>

      <div class="input-container">
        <button type="submit" class="submit-btn" value="Criar meu Burguer!" @click="submitForm">Criar meu Burguer!</button>
      </div>

    </form>
  </div>
</div>
</template>

<script>
export default{
  name:"BuguerForm"
}
</script>
<style scoped>
#burguer-form{
  max-width: 400px;
  margin: 0 auto;
}

.input-container{
  margin-bottom: 20px;
  display: flex;
  flex-direction: column;  
}
label{
  margin-bottom: 15px;
  font-weight: bold;
  color: #222;
  font-size: 18px;
  display: block;
  line-height: 1.5;
  text-transform: uppercase;
  letter-spacing: 1px;
  text-align: left;
  width: 100%;
  margin-top: 10px;
  border-left: 4px solid #fcba03;
}
#opcionias-container{
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  margin-top: 20px;
  padding-left: 20px;
  padding-right: 20px;
  border-left: 4px solid #fcba03;
  background: #f9f9f9;
}
#opcionais-title{
width: 100%;
}
.checkbox-container{
  display: flex;
  align-items: flex-start;
  width: 50%;
  margin-bottom: 20px;
}
.checkbox-container input,.checkbox-container span{
  width: auto !important;
}
.checkbox-container span{
  margin-left: 10px;
  font-weight: bold;
}
.submit-btn{
  background-color: #222;
  color: #fcba03;
  padding: 10px;
  border: 2px solid #222;
  cursor: pointer;
  font-size: 18px;
  text-transform: uppercase;
  letter-spacing: 1px;
  text-align: center;
  margin: 0 auto;
}
.submit-btn:hover{
  background-color:transparent;
color: #222;
}
</style>