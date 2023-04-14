
<script setup>
import { ref } from 'vue'
const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmarSenha = ref('')
const dataNascimento = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref('')
const linguagens = ref('')
const biografia = ref('')
const estados = [
  { nome: 'Acre', sigla: 'AC' },
  { nome: 'Alagoas', sigla: 'AL' },
  { nome: 'Amapá', sigla: 'AP' },
  { nome: 'Amazonas', sigla: 'AM' },
  { nome: 'Bahia', sigla: 'BA' },
  { nome: 'Ceará', sigla: 'CE' },
  { nome: 'Distrito Federal', sigla: 'DF' },
  { nome: 'Espírito Santo', sigla: 'ES' },
  { nome: 'Goiás', sigla: 'GO' },
  { nome: 'Maranhão', sigla: 'MA' },
  { nome: 'Mato Grosso', sigla: 'MT' },
  { nome: 'Mato Grosso do Sul', sigla: 'MS' },
  { nome: 'Minas Gerais', sigla: 'MG' },
  { nome: 'Pará', sigla: 'PA' },
  { nome: 'Paraíba', sigla: 'PB' },
  { nome: 'Paraná', sigla: 'PR' },
  { nome: 'Pernambuco', sigla: 'PE'},
  { nome: 'Piauí', sigla: 'PI'},
  { nome: 'Rio de Janeiro', sigla: 'RJ'},
  { nome: 'Rio Grande do Norte', sigla: 'RN'},
  { nome: 'Rio Grande do Sul', sigla: 'RS'},
  { nome: 'Rondônia', sigla: 'RO'},
  { nome: 'Roraima', sigla: 'RR'},
  { nome: 'Santa Catarina', sigla: 'SC'},
  { nome: 'São Paulo', sigla: 'SP'},
  { nome: 'Sergipe', sigla: 'SE'},
  { nome: 'Tocantins', sigla: 'TO'},
]
const usuario = ref(null)

  function submitForm() {
    const infoUsuario = {
      nome: nome.value,
      email: email.value,
      endereco: endereco.value,
      cidade: cidade.value,
      estado: estado.value,
      hobbies: hobbies.value,
      linguagens: linguagens.value,
      biografia: biografia.value
    }
    usuario.value = infoUsuario
  }
</script> 


<template>
  <form @submit.prevent="submitForm">
    <p>Nome</p>
    <input id="nome" type="text" v-model="nome" required>

    <p>Email</p>
    <input id="email" type="email" v-model="email" required>

    <p>Senha</p>
    <input id="senha" type="password" v-model="senha" required>

    <p>Confirme sua senha</p>
    <input id="confirmar-senha" type="password" v-model="confirmarSenha" required>

    <p>Data de nascimento</p>
    <input id="data-nascimento" type="date" v-model="dataNascimento" required>

    <p>Endereço</p>
    <input id="endereco" type="text" v-model="endereco">

    <p>Cidade</p>
    <input id="cidade" type="text" v-model="cidade">

    <p>Estado</p>
    <select id="estado" v-model="estado">
      <option value="">-- Selecione um estado --</option>
      <option v-for="(estado, index) in estados" :key="index" :value="estado.sigla">{{ estado.nome }}</option>
    </select>

    <p>Hobbies</p>
    <textarea id="hobbies" v-model="hobbies"></textarea>

    <p>Linguagens de programação</p>
    <input id="linguagens" type="text" v-model="linguagens">

    <p>Biografia</p>
    <textarea id="biografia" v-model="biografia"></textarea>
    <i>Quando você coloque todas as suas informações por favor toque no enviar</i>
    <i>Se você não preencher, não poderemos salvar suas informações</i>
    <button type="submit">Enviar</button>
  </form>

  <div v-if="usuario" class="resposta">
    <br>
      <h2>Informações do Usuário:</h2>
      <p>Nome: {{ usuario.nome }}</p>
      <p>Email: {{ usuario.email }}</p>
      <p>Endereço: {{ usuario.endereco }}, {{ usuario.cidade }}, {{ usuario.estado }}</p>
      <p>Hobbies: {{ usuario.hobbies }}</p>
      <p>Linguagens de programação: {{usuario.linguagens }} </p>
      <p>Biografia: {{ usuario.biografia }} </p>
    </div>
</template>

<style>
form {
  display: flex;
  flex-direction: column;
  max-width: 600px;
  margin: 0 auto;
}

p {
  font-size: 1.2rem;
  font-weight: bold;
  margin-top: 1rem;
}

input[type="text"],
input[type="email"],
input[type="password"],
textarea,
select {
  padding: 0.5rem;
  margin: 0.5rem 0;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1.2rem;
}

input[type="text"]:focus,
input[type="email"]:focus,
input[type="password"]:focus,
textarea:focus,
select:focus {
  outline: none;
  border-color: #000000;
}

button[type="submit"] {
  background-color: #ffbb00;
  color: #fff;
  font-size: 1.2rem;
  font-weight: bold;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-top: 1rem;
}

button[type="submit"]:hover {
  background-color: #000000;
}

.resposta{
  display: flex;
  flex-direction: column;
  max-width: 600px;
  margin: 0 auto;
}

</style>

