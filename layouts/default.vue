<template>
<div>

    <Header/>
    <Nuxt/> 
    <Footer/>

  
</div>
</template>




<style>
.footer {
  float: left;
  width: 100%;
  background: #000000;
}
.footer p {
  color: #9b9b9b;
}
.row {
  margin: 0;
  color: white;
  font-size: 12px;
}
h6 {
  color: #9b9b9b;
  font-size: 13px;
  font-family: arial black;
}

@media (max-width: 709px) {
  .derechos {
    position: absolute;
    left: 7px;
    width: 100%;
  }
}

@media (max-width: 659px) {
  .footer {
    display: grid;
    grid-auto-columns: 10%;
  }
}
</style>