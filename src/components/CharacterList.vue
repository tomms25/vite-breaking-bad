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
        <div>
           <SingleCharacter />
        </div>
    </div>
</template>

<style lang="scss" scoped>


</style>