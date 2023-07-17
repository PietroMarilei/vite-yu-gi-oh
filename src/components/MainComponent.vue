<script>
import { store } from '../store';


export default {
  data() {
    return {

      store,
    }
  },
  methods: {

  },
  props: {

  },

}
</script>

<template>
  <main>
    <div class="container bg-white">
      <div class="row bg-warning">
        <div class="dropdown p-2">
          <button class="btn btn-secondary dropdown-toggle p-2" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown button
          </button>
          <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </div>

      </div>
      <div class="row justify-content-center gy-3 p-5">
        <div class="my_found">
          <h2>Found ??? cards</h2>
        </div>

        <div class="col-sm-12 col-md-4 column" v-for="(singleCard, i) in store.cardArr" :key="i">
          <div class="my_card h-100">
            <img :src="singleCard.card_images[0].image_url" alt="" class="img-fluid ">
            <h3> {{ singleCard.name }}</h3>
            <div class="cardType">
              <p>{{ singleCard.type }}</p>
            </div>
            <!-- {{store.cardArr[2].card_images[0].image_url }} -->
          </div>



        </div>

      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

main {
  background-color: $card_yellow;
}

.my_found {
  color: white;
  background-color: rgb(47, 47, 47);
  padding: 1rem;
}

.my_card {
  background-color: $card_yellow;
  padding: 0.5rem;
  text-align: center;
  border-radius: 10px;

  h3 {
    font-size: medium;
    text-transform: uppercase;
    color: aliceblue;
    padding: 0.5rem 0;
  }
}
</style>