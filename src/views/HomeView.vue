<script setup>
import { ref, computed } from 'vue';

const contador = ref(0)
const bind = ref()
const array = ref([])

const sumar_uno = ()=>{
  contador.value = contador.value + 1
}

const restar_uno = ()=>{
  contador.value = contador.value - 1
}

const agregar_array = () =>{
  array.value.push(bind.value)

}

const color = computed(()=>{
  return contador.value > 0 ? 'green' : contador.value < 0 ? 'red' : 'blue'

})
</script>

<template>
  <main>
    <h1>{{ array }}</h1>
    <h1>Contador: <span :class="color">{{ contador }}</span></h1>
    <button @click="sumar_uno"> Más uno</button>
    <button @click="restar_uno">Menos uno</button>
    <input type="text" name="" id="" v-model="bind">
    <button @click="agregar_array">Agregar</button>
    <br>
    <h2 v-for="(item) in array">{{ item }}</h2>
    {{ bind }}
  </main>
</template>

<style scoped>

.blue{
  color:blue
}

.red{
  color:red
}

.green{
  color:green
}
</style>