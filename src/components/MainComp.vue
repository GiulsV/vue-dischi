<template>
  <main>
    <div class="container pb-4">
      <div>
        <SelectedComp
          :label="'All Genres'"
          @changedOption="genreFilter"
          :options="genres"
        />
      </div>
      <div class="row row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 d-flex justify-content-around">
        <CardComp
          class="col mt-4"
          v-for="(record, index) in filteredRecords" :key="index" :record="record"
        />
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import CardComp from '@/components/CardComp.vue'
import SelectedComp from '@/components/SelectedComp.vue'

export default {
    name: 'MainComp',
    props: {
      url: String
    },
    data(){
      return {
        records: [],
        selectedGenre: '',
      }
    },
    computed:{
      // funzione che aggiunge la lista dei generi in base a quelli presenti nell'array
      genres(){
        const genres = this.records.map((record)=>record.genre);
        const uniqueGenres = [...new Set(genres)];
        return uniqueGenres;
      },
      
      // associo l'array intero oppure filtrato per categoria in base al valore selezionato 
      filteredRecords(){
        let filteredByGenre = this.records;
        if (this.selectedGenre!==''){
              filteredByGenre = filteredByGenre.filter(({genre}) => genre === this.selectedGenre);
        }

        return filteredByGenre
      }
    },
    created(){
      axios.get(this.url).then(({ data, status })=>{
        console.log(status, data);
        if (status===200 && data.success){
          this.records = data.response;
         // console.log(this.records[0]);
        }
      })
      .catch((error)=>{
        console.log(error);
      });
    },
    methods: {
      // funzione filtro generi musicali
      genreFilter(selectedGenre){
          console.log('MainComp selectedGenre', selectedGenre);
          this.selectedGenre = selectedGenre;
      }
    },
    components: {
      CardComp,
      SelectedComp     
    }
}
</script>

 <style lang="scss" scoped>
main {
  background-color: #1e2d3b;
  height: calc(100vh - 100px);
  overflow: hidden;
}
</style>