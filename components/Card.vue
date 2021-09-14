<template>
  <div class="card" style="width: 18rem; text-decoration: none">
    <div class="tar">
      <nuxt-link :to="'/posts/' + id" style="text-decoration: none">
        <img
          :src="
            'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +
            gallery[1].medium
          "
          class="card-img-top"
          :alt="model"
        />
        <h6 style="color:black;text-align:center;font-size:19px">{{model}}</h6> 
        <li class="list-group-item" style="color: black; padding: 0; margin: 0">
          <p style="margin-top:10px;opacity:0.3;font-size:17px">
           PRECIO DESDE
          </p>
          <h6 style="position:relative;left:150px;bottom:38px;margin:0;font-size:16px;color:gray">{{detail.price.currency}} {{amount}}</h6>
        </li>
        <li class="list-group-item" style="color: black; padding: 0; margin: 0">
          <h6 style="color: #c60c1d">VER DETALLES DEL MODELO -></h6>
          <p class="p-3" style="opacity:0.3">
            Imagenes meramente ilustrativas no reportando la realidad exacta,
            pudiendo existir variaciones en la percepción
          </p>
        </li>
      </nuxt-link>
    </div>
  </div>
</template>
<style>
p {
  color: #000000;
}

.card {
  margin: 40px;
  float: left;
  width: 40%;
}
.card-group {
  width: 40%;
  text-decoration: none;
}

</style>
<script>
export default {
  name: "Card",
  props: ["id", "model", "gallery", "amount", "currency", "detail"],
};
</script>
