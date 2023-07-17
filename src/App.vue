<script >
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import { store } from './store';

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
    console.log('test');
    axios
    .get("https://db.ygoprodeck.com/api/v7/cardinfo.php")
    .then(response => {
      console.log('test 2');
      console.log(response);
    })
  },
}
</script>

<template>

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
