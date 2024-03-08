<script setup>
  import { ref, computed } from 'vue';

  const professor = ref({
    nome: 'Eduardo da Silva',
    disciplinas: [
      'Desenvolvimento Web II',
      'Desenvolvimento de Aplicativos para Dispositivos Móveis',
    ],
  });

  function possuiDisciplinas() {
    return professor.value.disciplinas.length > 0;
  }

  const contador = ref(0);
  const contador2 = ref(0)

  function incrementar() {
    contador.value++;
  }

  function decrementar() {
    if (contador.value > 0) {
      contador.value--;
    }
  }

  function reiniciar() {
    contador.value = 0;
  }

  let jeffrey = computed(() => {
    return contador.value + contador2.value
  });

let resultadoParImpar = computed(() => {

  v-if(resultadoParIpar){

contador % 2 == "par"

v-else {

  "Impar"
}

  }

});

</script>

<template>
  <div>
    <h1>Professor</h1>
    <p>Nome: {{ professor.nome }}</p>
    <p v-if="!possuiDisciplinas">O professor não possui disciplinas.</p>
    <div v-else>
      <p>O professor possui disciplinas.</p>
      <ul>
        <li v-for="disciplina in professor.disciplinas" :key="disciplina">
          {{ disciplina }}
        </li>
      </ul>
    </div>
  </div>


  <div class="contador">
    <h2>Contador</h2>
    <p>Valor: {{ contador }} </p>
    <button @click="incrementar">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <button @click="reiniciar">Reiniciar</button>
    <div
      :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }"
    >
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
</div>


<div>

</div>

</template>