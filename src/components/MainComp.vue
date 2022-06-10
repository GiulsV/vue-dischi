<template>
<main>
  <div class="container mt-5">
    <div v-if="cards.length > 0" class="row d-flex gy-5 gx-4 justify-content-between">
         <CardComp  class="col-2" 
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
</style>
