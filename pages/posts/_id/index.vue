<template>
  <div v-if="post">
    <div class="auto mb-5 p-1 pb-2">
      <div class="card1">
      <div class="card" style="width:500px">
        <img  :src="'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' + post.gallery[0].medium " class="card-img-top" :alt="post.model">
        <div class="card-body">
          <h5
            class="card-title"
            style="color: black; font-size: 27px; text-align: center"
          >
            {{ post.model }}
          </h5>
          <div class="card-body"></div>
          <ul class="list-group list-group-flush">
            <li class="list-group-item">
              {{post.detail.description}}
            </li>
            <li class="list-group-item">
              <h5>Caracteristicas</h5>
              {{post.specs.technical_details.features}}
              <li class="list-group-item">
              {{post.detail.characteristics.warranty}}
              </li>
              <li class="list-group-item">
              
              Color:{{post.detail.colors[0].name}}
              </li>
            <li class="list-group-item" style="font-size: 26px">
              {{ post.currency }} {{ post.amount  }}
            </li>
            <li class="list-group-item"></li>
          </ul>
        </div>
      </div>
      </div>
    </div>

    <div class="data p-5 m-5 col-5">
      <form class="dat">
        <div>
          <h1 style="text-align: center">INGRESÁ TUS DATOS</h1>
          <label for="floatingInput">Nombre</label>
          <div class="form-floating mb-3">
            <input
              type="text"
              class="form-control"
              id="floatingInput"
              required="required"
            />
            
          </div>

          <div class="form-floating mb-3">
            <label for="floatingInput">Telefono</label>
            <input
              type="text"
              class="form-control"
              id="floatingInput"
              required="required"
            />
            
          </div>
          <div class="form-floating">
            <label for="floatingPassword">Email</label>
            <input
              type="email"
              class="form-control"
              id="floatingInput"
              required="required"
            />
            
          </div>
          <div class="button">
            <div class="col-12">
              <button
                type="submit"
                class="btn btn-primary m-5"
                style="
                  background: #af1c1c;
                  border: 0;
                  height: 50px;
                  font-size: 17px;
                  width: 350px;
                "
              >
                ENVIARME LA COTIZACIÓN POR MAIL
              </button>
            </div>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>


<style>
.data {
  float: right;
}
.button {
  color: black;
}
.auto {
  width: 460px;
}
@media (max-width: 1165px) {
  .data {
    float: left;
    width: 80%;
  }
  .auto {
    width: 100%;
  }
  .button {
    float: left;
    margin: 0;
    padding: 0;
    position: relative;
    right: 70px;
  }
  .card1 {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 1000px;
  }
  .card-body {
    position: relative;
    top: 100px;
  }
  .data input {
    width: 300px;
  }
}
</style>


<script>
export default {

  head() {
    return {
      title: "Nissan Store",
    };
  },
  data() {
    return {
      posts: null,
    };
  },


  computed: {
    postsId() {
      return this.$route.params.id;
    },
    post() {
      if (this.posts === null) {
        return null;
      } else {
        return this.posts.results.find((item) => item.id === this.postsId);
      }
    },
  },



  methods: {
    async fetchCars() {
      this.posts = await this.$axios.$get(
        "https://4my1q6hsyo.api.quickmocker.com/product/",
        {
          headers: {
            Accept: "application/json",
            Authorization: "Bearer qwertyuiopasdfghjklzxcvbnm123456",
          },
        }
      );
      console.log(this.posts.results);
    },
    
  },
  
    async mounted() {
    this.fetchCars();
  },
};
</script>