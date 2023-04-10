
<script setup>
import { ref } from 'vue'
const nome = ref('')
const cores = ref([])
const aceitaTermos = ref(false)
const sexo = ref('')

</script>

<template>
  <form @submit.prevent="submitForm"></form>
  <p>Nome</p>
  <input id="nome" type="text" v-model="nome" required>

  <p>Email</p>
  <input id="email" type="email" v-model="email" required>

  <p>Senha</p>
  <input id="senha" type="password" v-model="senha" required>

  <p>Confima tua senha</p>
  <input id="confirmar-senha" type="password" v-model="confirmarSenha" required>

  <p>Digite sua data de nascimento:</p>
  <input type="date" v-model="dataNascimento" />


  <p>Endereço</p>
  <input id="endereco" type="text" v-model="endereco">

  <p>Cidade</p>
  <input id="cidade" type="text" v-model="cidade">

  <p>Estado</p>
  <select id="estado" v-model="estado">
    <option value="">-- Selecione um estado --</option>
    <option value="AC">Acre</option>
    <option value="AL">Alagoas</option>
    <option value="AP">Amapá</option>
    <option value="AM">Amazonas</option>
    <option value="BA">Bahia</option>
    <option value="CE">Ceará</option>
    <option value="DF">Distrito Federal</option>
    <option value="ES">Espírito Santo</option>
    <option value="GO">Goiás</option>
    <option value="MA">Maranhão</option>
    <option value="MT">Mato Grosso</option>
    <option value="MS">Mato Grosso do Sul</option>
    <option value="MG">Minas Gerais</option>
    <option value="PA">Pará</option>
    <option value="PB">Paraíba</option>
    <option value="PR">Paraná</option>
    <option value="PE">Pernambuco</option>
    <option value="PI">Piauí</option>
    <option value="RJ">Rio de Janeiro</option>
    <option value="RN">Rio Grande do Norte</option>
    <option value="RS">Rio Grande do Sul</option>
    <option value="RO">Rondônia</option>
    <option value="RR">Roraima</option>
    <option value="SC">Santa Catarina</option>
    <option value="SP">São Paulo</option>
    <option value="SE">Sergipe</option>
    <option value="TO">Tocantins</option>
  </select>
  <br>
  <br>
  <p>Hobbies</p>
  <textarea id="hobbies" v-model="hobbies"></textarea>

  <p>Linguagens de programação</p>
  <input id="linguagens" type="text" v-model="linguagens">

  <p>Biografia</p>
  <textarea id="biografia" cols="30" rows="10"></textarea>
</template>