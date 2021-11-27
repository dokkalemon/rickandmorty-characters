<template>
  <header>
      <h1>Rick & Morty Characters</h1>
  </header>
</template>

<script>
export default {
    name: 'Header',

}
</script>

<style scoped lang="scss">
@import '../styles/vars.scss';

header {
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom: 1px solid $tertiary-color;
    h1 {
        color: $secondary-color;
        font-weight: 400;
        font-size: 40px;
    }
}



</style>