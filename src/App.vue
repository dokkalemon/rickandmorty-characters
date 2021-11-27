<template>
  <div id="app">
    <!-- Header -->
    <Header @searchCharacter="search"/>

  <!-- Main -->
    <Main :characterArray="filterCharacter"/>

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
        this.takeDate()
    },
    
    data() {
        return {
            characterList: null,
            characterSearch: '',
        }
    },

    computed: {
      filterCharacter() {
        if (this.characterSearch === '') {
          return this.characterList
        }

        return this.characterList.filter( item => {
          return item.name.toLowerCase().includes(this.characterSearch.toLowerCase())
        })
      }
    },

    methods: {
        takeDate() {
            axios.get('https://api.sampleapis.com/rickandmorty/characters')
            .then(result => {
                this.characterList = result.data
            })
        },

        search(dato) {
          this.characterSearch = dato;
        }
    }

}
</script>

<style lang="scss">
@import '@/styles/global.scss'

</style>
