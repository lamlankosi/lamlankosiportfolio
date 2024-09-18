<template>
    <footer class="container-fluid">
        <div class="details">
                <p><i class="bi bi-envelope"></i> : lamlanomnganga9@gmail.com</p>
                <p><i class="bi bi-github"></i> :lamlankosi</p>
                <p><i class="bi bi-linkedin"></i> :Lamla Nomnganga</p>
                <p><i class="bi bi-telephone-fill"></i> :072938854</p>
            </div>
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
/* .details{
   gap:2rem;
    display:flex;
    margin-top: inherit;
    align-items: center;
    justify-content: center;
    margin-top:1rem;
} */
.container-fluid{
    background-color: black;
}
</style>