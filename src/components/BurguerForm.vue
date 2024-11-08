<template>
<div>
  <p>
    test
  </p>
  <div>
    <form action="" id="burguer-form" @submit="createBurguer">
      <div class="input-container">
        <label for="nome">Nome do Cliente:</label>
        <input type="text" id="nome" name="name" v-model="nome" placeholder="Digite o seu nome">
      </div>
      <div class="input-container">
        <label for="pao">Escolha o pão:</label>
        <select name="pao" id="pao" v-model="pao">
          <option value="">Selecione o seu pão</option>
          <option v-for="pao in paes" :key="pao.id" :value="pao.tipo" >{{ pao.tipo }} </option>
        </select>
      </div>

      <div class="input-container">
        <label for="pao">Escolha a carne:</label>
        <select name="pao" id="pao" v-model="pao">
          <option value="">Selecione o tipo de carne</option>
          <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo" >{{ carne.tipo }} </option>
        </select>
      </div>

      <div id="opcionais-container" class="input-container">
        <label id="opcionais-title" for="opicionais">Selecione os opcionais:</label>
        <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
          <input type="checkbox" id="quantidade" name="opicionais" v-model="opcionais" :value="opcional.tipo">
         <span>
          {{ opcional.tipo }}
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
  name:"BuguerForm",
  data(){
    return {
      nome:null,
      paes: null,
      carne: null,
      opcionaisdata: null,
      opcionais: [],
      pao: null,
      carne: null,
      status:"Solicitado",
      msg: null
    }
  },
  methods:{
    async getIngredientes(){
      try{
        const req = await fetch("http://localhost:3000/ingredientes");
        const data = await req.json();
        this.paes = data.paes;
        this.carne = data.carne;
        this.opcionaisdata = data.opcionais;
        this.carnes = data.carnes;
        this.opcionais = data.opcionais;
      }catch(error){
        console.error("Error fetching ingredientes:", error);
      }
    },
    async crateBurguer(){
      try{
        const req = await fetch("http://localhost:3000/burguer", {
          method: "POST",
          headers: {
            "Content-Type": "application/json"
          },
          body: JSON.stringify({
            nome: this.nome,
            pao: this.pao,
            carne: this.carne,
            opcionais: this.opcionais,
            status: this.status
          })
        });
        const data = await req.json();
        this.status = "Criado";
        this.msg = data.msg;
      }catch(error){
        console.error("Error creating burguer:", error);
        this.status = "Erro";
        this.msg = "Houve um erro ao tentar criar o burguer.";
      } 
    }
  },
  mounted(){
    this.getIngredientes();
  }
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
  flex-direction:column;
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