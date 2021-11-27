<template>
  <section class="card">
      <div class="card-image">
          <img :src="img" alt="">
      </div>
      <div class="card-info">
          <h2>{{ name }}</h2>
          <h3>{{ spieces }}</h3>
          <h3>{{ origin }}</h3>
      </div>
  </section>
</template>

<script>
export default {
    name: 'Card',

    props: {
        img: String,
        name: String,
        spieces: String,
        origin: String,
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';

.card {
    height: 430px;
    width: 250px;
    background-color: $tertiary-color;
    padding: 10px;
    border-radius: 20px;
    cursor: pointer;
    border: 1px solid $tertiary-color;
    margin: 10px;
    &:hover {
        background-color: $backg;
        border: 1px solid $tertiary-color;
    }
    .card-image {
        height: 250px;
        width: 100%;
        border-radius: 10px;
        overflow: hidden;
        img {
            height: 100%;
            width: 100%;
            object-fit: cover;
        }
    }
    .card-info {
        text-align: center;   
        h2{
            color: $primary-color;
            font-weight: 400;
            padding: 10px 0 5px 0;
        }
        h3 {
            font-weight: 300;
            color: $primary-color;
            padding: 5px 0 5px 0;
        }
       
    }
}

</style>