<template>
<header>
  <div class="container-fluid d-flex flex-start p-3">
      <img class="img-fluid" src="@/assets/logo.png" alt="logo spotify">
  </div>    
</header>
</template> 


<script>
export default {
    name: 'HeaderComp',
    props: { 
        
    }
}
</script>

<style lang="scss" scoped>
header{
    height: 100px;
    .container-fluid{
        background-color: rgb(46 58 70);
        img{
            min-width: 5%;
            width: 35px;
        }
    }    
}

    
</style>
