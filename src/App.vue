<template>
  <div>
    <titulo />
    <div class="centrar">
      <label class="tarea">Tarea </label>
      <input type="text" placeholder="Ingresa nueva tarea" v-model="nuevaTarea" />
      <button class="boton" @click="agregarTarea">Crear</button>
    </div>
    <lista />
    <div class="centrar">
      <ul>
        <li v-for="(tarea, $index) in tareas" :key="$index">{{ $index }} : {{ tarea }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Titulo from '@/components/Titulo.vue'
import Lista from '@/components/Lista.vue'

export default {
  name: 'App',
  components: {
    Titulo,
    Lista,
  },
  data: () => ({
    nuevaTarea: '',
    tareas: ['Ir al supermecado', 'Pagar Internet', 'Pagar Netflix'],
  }),
  methods: {
    agregarTarea() {
      this.tareas.push(this.nuevaTarea)
      this.nuevaTarea = ''
    },
  },
}
</script>
<style>
.centrar {
  display: flex;
  justify-content: center;
}
.tarea {
  font-weight: bold;
  margin-right: 5px;
}
.boton {
  margin-left: 5px;
}
</style>
