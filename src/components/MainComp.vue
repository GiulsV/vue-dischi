<template>
<main>
  <div class="container pb-4">
    <div v-if="cards.length > 0" class="row row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 d-flex justify-content-around">
         <CardComp  class="col mt-4" 
         v-for="(card, index) in cards" 
         :key="index" 
         :card="card"/>
    </div>   
  </div>
</main>

</template>

<script>
import axios from 'axios';
import CardComp from '@/components/CardComp.vue'
export default {
    name: 'MainComp',
     data(){
      return{
        cards: []
      }
    },
    props: {
        url: String
    },
    components: {
      CardComp
    },
    mounted(){
        this.loadData();
    },
    methods: {
        loadData(){
            axios.get(this.url)
            .then((response) => {
                    this.cards = response.data.response;
                    console.log(this.cards[0]);
            })
            .catch(
                  (error) =>{
                    console.log(error);
            })
        }
    }
}
</script>

<style lang="scss" scoped>

main{
  background-color: #1E2D3B;
  height: calc(100vh - 100px);
  overflow: hidden;
}
</style>
