<template>
  <div class="container-fluid d-flex flex-start p-3">
      <img class="img-fluid" src="@/assets/logo.png" alt="logo spotify">
  </div>
</template>

<script>
export default {
    name: 'HeaderComp',
    props: { 
        
    }
}
</script>

<style lang="scss" scoped>
    .container-fluid{
        background-color: blue;
        img{
            min-width: 5%;
            width: 35px;
        }
    }
    
</style>
