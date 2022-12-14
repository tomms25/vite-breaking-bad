<script>
import axios from 'axios';
import { createApp } from 'vue';
import AppHeader from './components/AppHeader.vue'
import CharacterList from './components/CharacterList.vue'

import { store } from './store.js';

export default{
  name: "App",
  components:{
    AppHeader,
    CharacterList
  },
  data() {
    return {
       store,
    }
  },
  methods:{
    getCharacters(){

      axios
      .get(store.apiURL)
      .then(res => {
        store.characterList = res.data.results;
      })
      .catch (err => {
        console.log("Errori", err);
      }

      );

    }
  },
  mounted() {
    this.getCharacters();
  }
}
</script>

<template>
  <!-- richiamo dentro lo store il titolo  -->
  <AppHeader :msg="store.titolo"/>
  <main>
    <CharacterList />
  </main>
</template>

<style lang="scss">
@use './style/general.scss';

main{
  padding-top: 20px;
}
</style>
