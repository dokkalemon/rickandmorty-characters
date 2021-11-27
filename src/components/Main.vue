<template>
    <main class="debug">
        
        <div class="cards" v-if="characterArray !== null">
        <Card 
        
        v-for="(character, index) in characterArray"
        :key="`char-${index}`"
        :img="character.image"
        :name="character.name"
        :spieces="character.species"
        :origin="character.origin"
        />
        </div>
        <div class="loader" v-else>
            <h1>Loading</h1>
        </div>
    </main>
</template>

<script>

import Card from '@/components/Card.vue'

export default {
    name: 'Main',
    components: {
        Card,

    },

    props: {
        characterArray: Array,
    }



}

</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';

main {
    
    
    padding: 30px;
    
    .cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    }

    .loader {
        height: 90vh;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        h1 {
            color: $primary-color;
            font-weight: 300;
            animation: scale 0.5s infinite alternate
        }

        @keyframes scale {
            from {transform: scale(1)}
            to {transform: scale(1.3)}
        }
    }
}

</style>