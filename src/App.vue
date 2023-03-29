<script setup>
import {ref, computed} from "vue";

import PropsUsuarioLogin from "./components/PropsUsuarioLogin.vue";
import PaginatePost from "./components/PaginatePost.vue";
import SpinnerLoading from './components/SpinnerLoading.vue';

const arrayProps = ref([]);
const paginacion = 20;
const contPaginacion = ref(paginacion);
const inicio = ref(0);
const final = ref(paginacion);
const tamanio = computed( () => arrayProps.value.length);
const cargando = ref(true);

//Tiempo de espera para ver el Spinner ...Cargando
/*
  fetch("https://jsonplaceholder.typicode.com/posts")
  .then((res) => res.json())
  .then((data) => (arrayProps.value = data))
  .finally( () => {
    setTimeout(() =>{
      cargando.value = false;
    },2000);    
  });
  */

  fetch("https://jsonplaceholder.typicode.com/posts")
  .then((res) => res.json())
  .then((data) => (arrayProps.value = data))
  .finally( () => cargando.value = false);
    

const next = () => {
  inicio.value += paginacion;
  final.value += paginacion;
};

const previus = () => {
  inicio.value -= paginacion;
  final.value -= paginacion;
};
</script>

<template>
    <SpinnerLoading v-if="cargando" />
      <div v-else>
        <h1>Vue JS</h1>
        
        <PaginatePost 
          @next="next"  
          @previus="previus"  
          :inicio="inicio"
          :final="final"
          :tamanio="arrayProps.length"
          class= "mb-2"/>

        <PropsUsuarioLogin
          v-for="prop in arrayProps.slice(inicio, final)"
          :key="prop.id"
          :title="prop.title"
          :body="prop.body"
          :id="prop.id"
        ></PropsUsuarioLogin>
      </div>
</template>

<style></style>