<script setup>
import { ref } from 'vue'
import watchlist from './components/watchlist.vue';
import {userWatchList} from '@/assets/watchList.js';

const titleInProgress = ref("")

const changeTitle = (titleProgess) => { titleInProgress.value = titleProgess  }
</script>

<template>
    <div class='row'>
      <div class='col left'>
          <ul>
              <li>Ici c'est fixe</li> 
              <li>Parent (nav, button, etc)</li>
          </ul>
          <span v-if="titleInProgress">▶ Lecture en cours: {{titleInProgress}} </span>
          <span v-else>Aucune lecture en cours </span>
      </div>
      <div class='col right'>

  
          <watchlist
            v-for="list in userWatchList"
            :series="list.series"
            :season="list.season"
            :episode="list.episode"
            :timeCursor="list.timeCursor"
            :title="list.title"
            @titleProgess="changeTitle"
          />
        
      </div>
  </div>

</template>

<style scoped>

</style>
