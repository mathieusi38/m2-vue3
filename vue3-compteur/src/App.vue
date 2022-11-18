<script setup>
import { ref } from 'vue'

const compteur = ref(0)

const increaseCount = () => { compteur.value++ }

const lessCount = () => { compteur.value-- }

</script>

<template>
  <div >
    
    <span class="counter-title">Compteur Title</span>
    <div class='container'>
        
      <div class='counter-container' >
        <span class="counter-display" :class="{red:compteur<0}"  >{{compteur}}</span>
      </div>

      <div class='buttons-container'>
          <button id='moins' @click="lessCount">-</button>
          <button id='plus' @click="increaseCount">+</button>
      </div>
    </div>
   
  </div>
</template>

<style scoped>

.red{
  color: red;
}

</style>
