<template>
  <header>
      <h1>Rick & Morty Characters</h1>

      <div class="input">
          <form action="">
              <input type="text" placeholder="Inserisci il nome per la ricerca">
              <button type="submit">Search</button>
              <button class="reset" type="reset">Reset</button>
          </form>
      </div>
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
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-bottom: 1px solid $tertiary-color;
    h1 {
        color: $secondary-color;
        font-weight: 400;
        font-size: 40px;
    }
    .input {
        form {
            display: flex;
            width: 700px;
            input {
                width: 100%;
                height: 30px;
                background-color: transparent;
                border: none;
                border-bottom: 1px solid $tertiary-color;
                color: white;
                font-size: 20px;
                margin-right: 5px;
                outline: none;
            }

            button {
                background-color: $tertiary-color;
                border: none;
                border-radius: 10px;
                padding: 5px;
                margin-right: 5px;
                color: white;
                font-size: 18px;

                &:active {
                    background-color: $secondary-color;
                    color: black;
                }
            }
            .reset {
                background-color: rgb(164, 107, 1)
            }
        }
    }
}



</style>