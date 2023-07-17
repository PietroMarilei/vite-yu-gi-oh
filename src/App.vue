<script >
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import LoaderComponent from './components/LoaderComponent.vue';
import { store } from './store';
import axios from "axios"

export default {
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
    LoaderComponent
  },
  data(){
    return {
      store,
      isload: false
    }
  }, 
  methods: {

  },
  created() {
    setTimeout(()=>{
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then(response => {
          //store.cardArr.push(response.data.data[0])
          store.cardArr = response.data.data
          console.log(this.store.cardArr);
          this.isload = true;
          console.log(this.isload);
        })
    },1000)
    
  },
}
</script>

<template>
  <!-- {{ store.cardArr[2]}} -->
  
  <HeaderComponent />
  <LoaderComponent v-if="isload == false"/>
  <div v-else>
    <MainComponent/>

  </div>

  <FooterComponent/>

</template>

<style lang="scss">
  @use "./assets/scss/main.scss" as *;
  @use "./assets/scss/partials/variables.scss" as *;
  
  body {
    background-color: lightslategray;
  }
</style>
