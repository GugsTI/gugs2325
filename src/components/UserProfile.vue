<script setup>
import { defineProps } from 'vue';

// eslint-disable-next-line no-unused-vars
const props = defineProps({
  userData: {
    type: Object,
    default: () => ({})
  }
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
</script>



<template>
  <div class="forms2">
    <h4 class="title2">Dados do Usuário</h4>
    <p><strong>Email:</strong> {{ userData.email }}</p>
    <p><strong>Nome:</strong> {{ userData.nome }}</p>
    <p><strong>Data de Nascimento:</strong> {{ userData.dataN }}</p>
    <p><strong>Endereço:</strong> {{ userData.endereço }}</p>
    <p><strong>Cidade:</strong> {{ userData.cidade }}</p>
    <p><strong>Estado:</strong> {{ estados[userData.estado] }}</p>
    <p><strong>Hobbies:</strong> {{ userData.hobbies }}</p>
    <p><strong>Linguagens de Programação:</strong> {{ userData.linguagens }}</p>
    <p><strong>Biografia:</strong> {{ userData.biografia }}</p>
    <p><strong>Senha:</strong>{{ userData.senha }}</p>
    <p><strong>Senha:</strong>{{ userData.senha }}</p>
  </div>
</template>



<style scoped>
.forms2 {
  background-color: blue;
  width: 45vw;
  min-height: 95vh;
  border-radius: 20px;
  padding: 40px;
  color: aliceblue;
  margin-left: 30%;
  margin-bottom: 170px;
}
.title2 {
  margin-bottom: 20px;
}
</style>
