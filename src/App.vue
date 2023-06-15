

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
function limpardados (){
  email.value = ""
  nome.value = ""
  dataN.value = ""
  endereço.value = ""
  cidade.value = ""
  estado.value = ""
  senha.value = ""
  confirmaçao.value = ""
  botaoDados.value = false
}




</script>

  
<template class="cor">
 
  <form>
  <div class="row">
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
    <div class="col">
      <input type="password" v-bind:value="senha" v-on:input="event => senha = event.target.value" class="form-control" placeholder="Insira sua senha" name="pswd">
      <input type="password" v-bind:value="confirmaçao" v-on:input="event => confirmaçao = event.target.value" class="form-control" placeholder="confirmaçao de senha" name="pswd">

      
    </div>
  </div>
</form>


<button class="form-control form-control-lg" v-on:click="botaoDados = true ">mostrar dados do usuario</button>
<button class="form-control form-control-lg" @click="limpardados"> limpar dados</button>

<div class="form-control" v-if = "botaoDados" >
<h4 class="form-control forms-control-lg" >Dados usuário</h4>
    <p>Email digitado: {{ email }}</p>
<p>Nome digitado:{{ nome }}</p>
<p>Data de nascimento digitado:{{ dataN }}</p>
<p>Endereço digitado:{{ endereço }}</p>
<p>Cidade digitado:{{ cidade }}</p>
<p>Estado digitado:{{ estado }}</p>
<p>Senha digitado:{{ senha }}</p>
<p>Confirmaçao digitado:{{ confirmaçao }}</p>
</div>

</template>

<style scoped>

div{
  background-color: rgba(188, 253, 253, 0.918);
}

</style>

