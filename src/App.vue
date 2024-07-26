<script setup>
import { ref } from 'vue';
import UserForm from './components/UserForm.vue';
import UserProfile from './components/UserProfile.vue';

const showForm = ref(true);
const userData = ref({});

function updateUserData(data) {
  userData.value = data;
  showForm.value = false;
}

if(showForm.value == true){
  alert(`Preencha todos os campos e clique em salvar abaixo:`)
}
</script>


<template>

  <div class="botao">
    <button @click="showForm = true" class="btn btn-primary">Mostrar Formulário</button>
    <button @click="showForm = false" class="btn btn-secondary">Mostrar Dados</button>

    <UserForm v-if="showForm" @update:userData="updateUserData" />
    <UserProfile v-else :userData="userData" />
  </div>
</template>


<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

.btn {
  margin: 10px;
}
</style>
