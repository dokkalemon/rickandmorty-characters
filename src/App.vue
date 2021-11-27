<template>
  <div id="app">
    <!-- Header -->
    <Header />

  <!-- Main -->
    <Main :characterArray="characterList"/>

  </div>
</template>

<script>
import axios from 'axios'
import Header from '@/components/Header.vue'
import Main from '@/components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },

      created() {
        this.prova()
    },
    
    data() {
        return {
            characterList: null,
        }
    },

    methods: {
        prova() {
            axios.get('https://api.sampleapis.com/rickandmorty/characters')
            .then(result => {
                this.characterList = result.data
            })
        }
    }

}
</script>

<style lang="scss">
@import '@/styles/global.scss'

</style>
