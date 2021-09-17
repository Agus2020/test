<template>
<div class="cardautos">
      <nuxt-link :to="'/posts/' + id">
  <b-card
    no-body
    style="max-width: 20rem;"
    :img-src="
            'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +
            gallery[1].medium
          "
  >
    <template #header>
      <h4 class="mb-0 cardtituloauto text-center">{{model}}</h4>
    </template>

    <b-card-body>
      <b-card-text class="text-center textoautoimagenes">
            Imagenes meramente ilustrativas no reportando la realidad exacta,
            pudiendo existir variaciones en la percepción
      </b-card-text>
    </b-card-body>

    <b-list-group flush class="carddetallesauto text-center">
      <b-list-group-item>VER DETALLES DEL MODELO -></b-list-group-item>
    </b-list-group>

    <b-card-body class="cardprecioauto text-center">
    {{detail.price.currency}} {{detail.price.amount}}
    </b-card-body>
  </b-card>

      </nuxt-link>
</div>

</template>
<style>
  .cardautos{
    width:350px;
    float:left;
    margin:15px;
    text-decoration: none;
    opacity:0.8;
  }
  .cardautos:hover{
    opacity:1;
  }
  .cardtituloauto{
    color:black;
    font-size:19px;
  }
  .carddetallesauto{
    color: #c60c1d;
    padding:10px;
  }
    .textoautoimagenes{
    color:black;
    opacity:0.3;
  }

  .cardprecioauto{
    color:black;
    opacity:0.6;
    font-size:17px;
  }
  .precioautogeneral{
    color:black;
    display:flex;
    float:right;
  }
  a:hover{
    text-decoration:none;
  }
</style>
<script>
export default {
  name: "Card",
  props: ["id", "model", "gallery", "amount", "currency", "detail"],
};
</script>
