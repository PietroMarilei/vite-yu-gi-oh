<script >
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import { store } from './store';
import axios from "axios"

export default {
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },
  data(){
    return {
      store,
    }
  }, 
  methods: {

  },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then(response => {
        //store.cardArr.push(response.data.data[0])
        store.cardArr = response.data.data
        console.log(this.store.cardArr);
      })
  },
}
</script>

<template>
  {{ store.cardArr[2]}}
  <HeaderComponent/>

  <MainComponent/>

  <FooterComponent/>

</template>

<style lang="scss">
  @use "./assets/scss/main.scss" as *;
  @use "./assets/scss/partials/variables.scss" as *;
  
  body {
    background-color: lightslategray;
  }
</style>
