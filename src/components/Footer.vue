<template>
    <footer class="footer">
      <div class="row">
          <p class="lead">Lamlankosi Nomnganga's Portfolio &copy;<span class="shadow">{{ cYear }}</span>
          </p>
          
      </div>
    </footer>
</template>
  
<script>
export default {
    name: 'footerComp',
    data(){
        return{
           cYear: new Date().getUTCFullYear()
       }
  }
}
</script>
  
<style scoped>
.details{
   gap:2rem;
    display:flex;
    margin-top: inherit;
    align-items: center;
    justify-content: center;
    margin-top:1rem;
}

@media screen and (max-width: 800px) {
    .details{
        display: flow;
}
}
</style>