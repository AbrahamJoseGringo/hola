<script setup>
import { ref } from 'vue'
const nome = ref('')
const cores = ref([])
const aceitaTermos = ref(false)
const sexo = ref('')

</script>

<template>
  <input v-model="nome" />
  <p>Nome digitado é: </p>
<br>
<p>Digite sua senha:</p>
<input type="password" v-model="senha" />
<br>
<br>
<p>Digite seu email:</p>
<input type="email" v-model="email" />
<br>
<br>
<p>Digite sua idade:</p>
<input type="number" v-model="idade" />
<br>
  <label for="aceitaTermos">Aceito os termos</label>
  <input type="checkbox" v-model="aceitaTermos" />
  <p>Aceita os termos: </p>
  <p>Cores favoritas: </p>
  <select v-model="cores" multiple>
    
    <option value="vermelho">Vermelho</option>
    <option value="verde">Verde</option>
    <option value="azul">Azul</option>
    <option value="amarelo">Amarelo</option>
  </select>
 <br>
  <label for="sexo">Sexo  </label>
  <input type="radio" v-model="sexo" value="masculino" /> Masculino
  <input type="radio" v-model="sexo" value="feminino" /> Feminino
 
</template>
