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
          ;
        })
    },3000)
    
  },
}
</script>

<template>
  <!-- {{ store.cardArr[2]}} -->
  
  
  <LoaderComponent v-if="isload == false"/>
  <div v-else>
    <HeaderComponent />
    <MainComponent/>

  </div>


</template>

<style lang="scss">
  @use "./assets/scss/main.scss" as *;
  @use "./assets/scss/partials/variables.scss" as *;
  
  body {
    background-color:#0D0D0D;
  }
</style>
