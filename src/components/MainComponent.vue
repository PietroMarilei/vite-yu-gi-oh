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
    <div class="container">
      <div class="row">
        <h1 class=" color-primary">dropdown</h1>
        <div class="row">
          <div class="col-sm-12 col-md-4 column" v-for="(singleCard,i) in store.cardArr" :key="i" >
            <div class="my_card h-100">
              <img :src="singleCard.card_images[0].image_url" alt="" class="img-fluid ">
              <h3> {{singleCard.name }}</h3>
              <div class="cardType">
                <p>{{ singleCard.type }}</p>
              </div>
                <!-- {{store.cardArr[2].card_images[0].image_url }} -->
            </div>
            
            
            
          </div>
          
        </div>
      </div>
    </div>
  

</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

.my_card {
  background-color: $card_yellow;
  padding: 0.5rem;
}
    
</style>