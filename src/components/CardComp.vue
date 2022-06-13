<template>
   <div class="card align-items-center pt-3 mx-3">
    <img :src="record.poster" :alt="record.title" class="card-img-top" />
    <div class="card-body">
      <h5 class="card-title text-center mt-3">
        {{ record.title }}
      </h5>
      <div class="pb-5 d-flex flex-column .justify-content-start text-center">
        <span class="card-text">
          {{ record.author }}
        </span>
        <span class="card-text">
          {{ record.year }}
        </span>
      </div>
    </div>
  </div> 
</template>

<script>
export default {
  name: "CardComp",
  props: {
    record: Object,
  },
};
</script>


<style lang="scss" scoped>
.card {
  background-color: #2f3a46;
  height: 350px;
  width: 200px;
  img {
    width: 70%;
  }
  .card-title {
    color: white;
    text-transform: uppercase;
  }
  .card-text {
    color: rgb(122 127 128);
  }
}
</style>
