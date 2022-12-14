<script>
import SingleCharacter from './SingleCharacter.vue'

import{ store } from '../store.js';


export default {
    name:"CharacterList",
    components: {
        SingleCharacter
    },
    data () {
        return {
            store,
        }
    }
}

</script>


<template>
    <section class="container"></section>
    <div class="row">
        <div v-for="character in store.characterList" :key="character.id" class="col-6 col-md-4 col-lg-3 mb-5">
           <SingleCharacter :info="character" />
        </div>
    </div>
</template>

<style lang="scss" scoped>


</style>