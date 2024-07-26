<template>
  <div class="forms">
    <form @submit.prevent="submitForm">
      <div class="col">
        <input type="text" v-model="formData.nome" class="form-control" placeholder="Insira seu nome" />
        <input type="email" v-model="formData.email" class="form-control" placeholder="Enter email" />
        <input type="date" v-model="formData.dataN" class="form-control" placeholder="Insira sua data de nascimento" />
        <input type="text" v-model="formData.endereço" class="form-control" placeholder="Insira seu endereço" />
        <input type="text" v-model="formData.cidade" class="form-control" placeholder="Insira sua cidade" />
        
        <select v-model="formData.estado" class="form-select mt-3">
          <option disabled value="">Selecione o estado</option>
          <option v-for="(nome, codigo) in estados" :key="codigo" :value="codigo">
            {{ nome }}
          </option>
        </select>
        
        <input type="text" v-model="formData.hobbies" class="form-control" placeholder="Insira seus hobbies" />
        <input type="text" v-model="formData.linguagens" class="form-control" placeholder="Insira suas linguagens de programação" />
        <textarea v-model="formData.biografia" class="form-control" placeholder="Insira sua biografia"></textarea>
        
        <input type="password" v-model="formData.senha" class="form-control" placeholder="Insira sua senha" />
        <input type="password" v-model="formData.confirmaçao" class="form-control" placeholder="Confirmação de senha" />
        
        <button type="submit" class="btn btn-primary">Salvar</button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref, defineEmits } from 'vue';

// eslint-disable-next-line vue/valid-define-emits
const emit = defineEmits();

const formData = ref({
  nome: '',
  email: '',
  dataN: '',
  endereço: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagens: '',
  biografia: '',
  senha: '',
  confirmaçao: ''
});

const estados = {
  AC: 'Acre',
  AL: 'Alagoas',
  AP: 'Amapá',
  AM: 'Amazonas',
  BA: 'Bahia',
  CE: 'Ceará',
  DF: 'Distrito Federal',
  ES: 'Espírito Santo',
  GO: 'Goiás',
  MA: 'Maranhão',
  MT: 'Mato Grosso',
  MS: 'Mato Grosso do Sul',
  MG: 'Minas Gerais',
  PA: 'Pará',
  PB: 'Paraíba',
  PR: 'Paraná',
  PE: 'Pernambuco',
  PI: 'Piauí',
  RJ: 'Rio de Janeiro',
  RN: 'Rio Grande do Norte',
  RS: 'Rio Grande do Sul',
  RO: 'Rondônia',
  RR: 'Roraima',
  SC: 'Santa Catarina',
  SP: 'São Paulo',
  SE: 'Sergipe',
  TO: 'Tocantins'
};

function submitForm() {
if(formData.value.nome == ''  || formData.value.email == '' || formData.value.dataN == ''  || formData.value.endereço == ''||  formData.value.cidade == ''  || formData.value.estado == '' || formData.value.hobbies == ''|| formData.value.biografia == ''|| formData.value.linguagens == '' || formData.value.senha == '' || formData.value.confirmaçao == ''  ){
  alert(`Existem campos vázios.`)
}

  else if (formData.value.senha !== formData.value.confirmaçao) {
    alert('As senhas não coincidem.');
    return;
  }
  emit('update:userData', formData.value);
}




</script>

<style scoped>
.forms {
  background-color: blue;
  width: 45vw;
  min-height: 10;
  border-radius: 20px;
  padding: 40px;
  margin-bottom: 170px;
  margin-left: 30%;
}

.form-control, .form-select {
  margin-bottom: 15px;
}
</style>
