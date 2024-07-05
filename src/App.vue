

<script setup>
import { ref } from 'vue'

const email = ref('')
const nome = ref('')
const dataN = ref('')
const endereço = ref('')
const cidade = ref('')
const estado = ref('')
const senha = ref('')
const confirmaçao = ref('')
const botaoDados = ref('')
const numeroCartao = ref('')
const cvv = ref('')

function limpardados (){
  email.value = ""
  nome.value = ""
  dataN.value = ""
  endereço.value = ""
  cidade.value = ""
  estado.value = ""
  senha.value = ""
  numeroCartao.value = ""
  cvv.value = ""
  confirmaçao.value = ""
  botaoDados.value = false
}
const senhas = senha.value && confirmaçao.value
function validacao(){
  if (email.value == "" || nome.value == "" || dataN.value == ""||  endereço.value == ""|| cidade.value == ""|| estado.value == ""|| numeroCartao.value == ""||cvv.value == ""   ){
    alert(`Existe campos vazio!`)
  }
  else{
    alert(`Confirmando...`)
  }
if(senha.value == "" && confirmaçao.value == ""){
alert(`preencha o campo "SENHA"`)
}
else{
alert(`confirmando senha...`)
}
  if (confirmaçao.value == senha.value ){
    alert(`Confirmado!`)
  }
  else{
    alert(`As senhas não coincidem.`)
  }
}
 




</script>

  
<template class="cor">
 
  <form>
  <div class="forms">
    <div class="col">
      <input type="text" v-bind:value="email" v-on:input="event => email = event.target.value" class="form-control"
          placeholder="Enter email" name="email ">
        <input type="text" v-bind:value="nome" v-on:input="event => nome = event.target.value" class="form-control"
          placeholder="Insira seu nome">
        <input type="text" v-bind:value="dataN" v-on:input="event => dataN = event.target.value" class="form-control"
          placeholder="Insira sua data de nascimento">
        <input type="text" v-bind:value="endereço" v-on:input="event => endereço = event.target.value"
          class="form-control" placeholder="insira seu endereço">
        <input type="text" v-bind:value="cidade" v-on:input="event => cidade = event.target.value" class="form-control"
          placeholder="Insira sua cidade">
     

     <input type="text" v-bind:value="estado" v-on:input="event => estado = event.target.value" class="form-control"
          placeholder="Insira seu estado">

          <input type="text" v-bind:value="numeroCartao" v-on:input="event => numeroCartao = event.target.value" class="form-control"
          placeholder="Insira o número do cartão de crédito">

          <input type="text" v-bind:value="cvv" v-on:input="event => cvv = event.target.value" class="form-control"
          placeholder="Insira o cvv do seu cartão">
          
          
          <div class="select">
            <br>
          <h6 class="title">INSIRA O UF DO ESTADO ABAIXO:</h6>


     <select v-bind:value="estado" v-on:input="event => estado = event.target.value" class="form-select mt-3" placeholder="Estado:">
     <option>AC</option>
     <option>AL</option>
     <option>AP</option>
     <option>AM</option>
     <option>BA</option>
     <option>CE</option>
     <option>DF</option>
     <option>ES</option>
     <option>GO</option>
     <option>MA</option>
     <option>MT</option>
     <option>MS</option>
     <option>MG</option>
     <option>PA</option>
     <option>PB</option>
     <option>PR</option>
     <option>PE</option>
     <option>PI</option>
     <option>RJ</option>
     <option>RN</option>
     <option>RS</option>

     <option>RO</option>
     <option>RR</option>
     <option>SC</option>
     <option>SP</option>
     <option>SE</option>
     <option>TO</option>
   </select>
          </div>
   

    </div>
    <br>
    <div class="select">
      <h6 class="title">COLOQUE E CONFIRME SUA SENHA ABAIXO:</h6>
    </div>
    <div class="col">
      <input type="password" v-bind:value="senha" v-on:input="event => senha = event.target.value" class="form-control" placeholder="Insira sua senha" name="pswd">
      <input type="password" v-bind:value="confirmaçao" v-on:input="event => confirmaçao = event.target.value" class="form-control" placeholder="confirmaçao de senha" name="pswd">


      
    </div>
  </div>
</form>

<div class="bt1">
<button class="btn btn-danger" v-on:click="botaoDados = true ">mostrar dados do usuario</button>
</div>
<div class="bt2">
<button class="btn btn-success" @click="limpardados"> limpar dados</button>
</div>

<div class="forms2" v-if = "botaoDados" >
<h4 class="title2" >Dados usuário</h4>
    <p>Email digitado: {{ email }}</p>
<p>Nome digitado: {{ nome }}</p>
<p>Data de nascimento digitado: {{ dataN }}</p>
<p>Endereço digitado: {{ endereço }}</p>
<p>Cidade digitado: {{ cidade }}</p>
<p>Estado digitado: {{ estado }}</p>
<p>Número cartão: {{ numeroCartao }}</p>
<p>CVV do cartão: {{ cvv }}</p>
<p>Senha digitado: {{ senha }}</p>
<p>Confirmaçao digitado: {{ confirmaçao }}</p>
<div class="bt3">
  <button class="btn btn-success" v-on:click="validacao">Confirmação</button>
</div>
</div>

</template>

<style scoped>
.bt1 {
    margin-left:12.5%;
    margin-top: -5%;
    align-content: center;

}

.bt2 {
  margin-left:28.5%;
    margin-top: -2.4%;
    align-content: center;

}
.bt3{
  margin-left:12.5%;
    margin-top: 10%;
    align-content: center;
}

.forms {
    background-color: blue;
    width: 45vw;
    min-height: 95vh;
    border-radius: 20px;
    padding: 40px;
    margin-top: 0.5%;
    margin-left: 3%;

}
.forms2{
  background-color: blue;
    width: 45vw;
    min-height: 95vh;
    border-radius: 20px;
    padding: 40px;
    color: aliceblue;
    margin-top: -42.3%;
    margin-left: 50%;
}
.dadosUsu {
    width: 30%;
    height: 30px;
    font-size: 10px;
    margin-left: 50%;
    margin-top: 15%;

}

.dadosUsu1 {
    width: 30%;
    height: 30px;
    font-size: 10px;
    margin-left: -70%;
}

.container {
    display: flex;
    gap: 2rem;
    justify-content: center;
    margin-top: 1rem;
    margin-left: 35%;
}

.title {
    text-decoration-color: azure;

}


.select {
    align-items: center;
    text-align: center;
    color: aliceblue;

}


</style>

