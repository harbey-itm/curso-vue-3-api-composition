<script setup>

    defineProps(["inicio", "final", "tamanio"]);
    const emit = defineEmits(["next", "previus"]);

</script>

<template>
  <div class="btn-group" role="group" aria-label="Basic example">
    <button 
      @click="$emit('previus')"  
      type="button" 
      class="btn btn-primary"
      :disabled = "inicio <= 0"
      >Anterior {{ inicio }}
    </button>
    <button 
    @click="$emit('next')"     
    type="button" 
    class="btn btn-primary"
    :disabled="final >= tamanio"
    >Siguiente {{ final }}
  </button>
  </div>
</template>