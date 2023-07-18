<script>
import { store } from '../store';
import axios from 'axios';


export default {
  data() {
    return {
      store,
      selectedType: '',
      
    }
  },
  methods: {
    // getArchetype() {
    //   console.log(this.selectedType);
    //   axios
    //     .get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
    //       params: {
    //         archetype: this.selectedType,
    //       }})
          
        
    //     .then(response => {
    //       //store.cardArr.push(response.data.data[0])
    //       store.cardArr = response.data.data
    //       console.log(this.store.cardArr);
    //       this.isload = true;
          
    //     });
    // }
  },
  props: {

  },

}
</script>

<template>
  <main>
    <div class="container bg-white">
      <div class="row bg-warning">
        <form @submit.prevent="$emit('mySearch')" action="">
          <select  v-model="selectedType" class="form-select" >         
            <option  v-for="(singleType, i) in store.typeArr" :key="i" :value="singleType.archetype_name">{{ singleType.archetype_name }}</option>         
          </select>

          <button type="submit" class="btn btn-primary">Submit</button>

        </form>
        
        

        

      </div>
      <div class="row  gy-3 p-5">
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
  border-radius: 5px;

  h3 {
    font-size: medium;
    text-transform: uppercase;
    color: aliceblue;
    padding: 0.5rem 0;
  }
}
</style>