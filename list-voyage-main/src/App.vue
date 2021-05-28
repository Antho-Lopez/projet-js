<template>
  <div class="entete">
    <div class="header">
      <router-link class="link" :to="{ name: 'destinations' }"><img class="logo-style" src="./assets/logo.png"></router-link>
      <router-link class="link" :to="{ name: 'souhaits' }"><img class="planning-style" src="./assets/planning.jpg">Mon planning</router-link>
    </div>
  </div>
  <router-view></router-view>
  
</template>
<script>

</script>
<style scoped>

  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

  .header{
    width: 80vw; 
    margin-left: 10vw;
    padding-top: 20px;
    padding-bottom: 20px;
    display: flex; 
    justify-content: space-between;
    align-items: center;
  }

  .entete{
    border-bottom: 1px solid #BBBBBB;
  }

  .link{
    text-decoration: none; 
    font-family: 'Roboto';
    font-weight: bold; 
    color: #292929;
    display: flex;
    align-items: center;
    font-size: 26px;
  }

  .logo-style{
    width: 20vw;
  }

  .planning-style{
    width: 3vw;
    margin-right: 10px;
  }
  
</style>
