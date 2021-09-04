<template>
  <div class="card" style="width: 18rem;text-decoration:none;">
    <div class="tar">
      <nuxt-link :to="'/posts/' + id" style="text-decoration:none">
        <img
          :src="
            'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +
            gallery[1].medium
          "
          class="card-img-top"
          :alt="model"
        />
        <div class="card-body">
          <ul class="list-group list-group-flush">
            <li
              class="list-group-item"
              style="font-size: 30px;font-family:calibri; text-align: center;color:black"
            >
              {{ model }}
            </li>

            <li class="list-group-item"></li>
          </ul>
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item" style="text-align: center;color:black">
            {{ detail.main_description }}
          </li>
          <li class="list-group-item">
            <p
              style="font-family: calibri; font-size: 21px;text-align:center"
            >
              {{ currency }} {{ amount }}
            </p>
          </li>
        </ul>
      </nuxt-link>
    </div>
  </div>
</template>
<style>
p {
  color: #000000;
}
.tar {
  transition: transform 0.2s;
}
.tar:hover {
  transform: scale(1.1);
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
