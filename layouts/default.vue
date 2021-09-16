<template>
<div>

    <Header/>
    <Nuxt/> 
    <Footer/>

  
</div>
</template>




<style>
.alayout{
  color: white;
}
.footerlayout {
  float: left;
  width: 100%;
  background: #000000;
}
.derechoslayout p {
  color: #9b9b9b;
}
.rowlayout {
  margin: 0;
  color: white;
  font-size: 12px;
}
.h6layout {
  color: #9b9b9b;
  font-size: 13px;
  font-family: arial black;
}
.footertext a{
  color:white;
}
@media (max-width: 709px) {
  .derechoslayout {
    position: absolute;
    left: 7px;
    width: 100%;
  }
}

@media (max-width: 659px) {
  .footerlayout {
    display: grid;
    grid-auto-columns: 10%;
  }
}
</style>