<template>

<div class="card bg-dark text-white" style="border:0;margin:0;width:100%">
  <img src="../static/Banner.jpg" class="card-img" alt="...">
  <div class="card-img-overlay">
    <div class="texto">
      <h1 class="card-title">AHORA ES ONLINE</h1>
      <pre class="card-text">
Con Nissan Store, podés accedera tu nuevo 0km con todos
los servicios asociados desde la comodidad de tu sofá. 
Probanos!</pre>
      <div class="d-grid gap-2 col-6 mx-auto">
        <nuxt-link to='posts'>
          <span class="spa">
            <button class="btn btn-primary" type="button" style="background:#AF1C1C;border:0;height:50px;position:relative;right:168px;top:30px;font-size:17px;width:350px;">INGRESAR A NISSAN STORE</button>
          </span>
        </nuxt-link> 
      </div>
    </div>   
  </div>


</div>
</template>
<style>
  *{
    padding:0;
    margin:0;
  }
  .card-title{
    color:#AF1C1C;
    font-family:arial black;
    font-size:60px;
  }
  pre{
    color:black;
    font-size:20px;
    font-family:arial;
  }
  @media (max-width:828px)
  {
    .card-title{
      font-size:30px;
    }
  }
  @media (max-width:690px)
  {
    pre{
      font-size:16px;
    }
  }
    @media (max-width:581px)
  {
    pre{
      font-size:13px;
    }
  }
</style>
<script>
    export default {
        head(){
            return{
                title:'Nissan Store',
                meta:[
                    {
                        hid: "description",
                        name:"description",
                        content: "Website"
                    }   
                ],
                htmlAttrs:{
                    lang:'es'
                }
            }
        }
    }
</script>