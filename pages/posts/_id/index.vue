<template>
  <div v-if="post">
    <div class="auto mb-5 p-1 pb-2">
      <div class="card1">
        <div class="card" style="width: 500px; width: 35rem">
          <div>
            <b-carousel
              id="carousel-1"
              v-model="slide"
              controls
              indicators
              background="gray"
              :interval="5000"
              img-width="2000"
              img-height="480"
              @sliding-start="onSlideStart"
              @sliding-end="onSlideEnd"
            >
              <div style="opacity: 0.9">
                <b-carousel-slide
                  v-for="item in post.gallery"
                  :key="item.id"
                  :img-src="
                    'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +
                    item.medium
                  "
                >
                </b-carousel-slide>
              </div>
            </b-carousel>
          </div>
          <table class="d-name d-md-table table text-muted text-center">
            <tbody>
              <tr class="fw-bold">
                <td>
                  <ul class="list-group list-group-flash" style="width: 90%">
                   
                                     <li class="list-group-item">
                      {{ post.model }}
                    </li>
                    <li class="list-group-item">
                      {{ post.detail.description }}
                    </li>

                    <li class="list-group-item">
                      {{ post.detail.price.currency }} {{ post.amount }}
                    </li>
                    <li class="list-group-item">
                      {{ post.detail.characteristics.warranty }}
                    </li>
                  </ul>
                </td>
              </tr>
              <label
                class="text-left"
                v-for="item in post.detail.colors"
                :key="item"
              >
                , {{ item.name }}</label
              >
            </tbody>
          </table>
        </div>
      </div>
    </div>
    <div class="data p-5 m-5 col-5">
      <form class="dat" v-if="verification">
        <div>
          <h1 style="text-align: center">INGRESÁ TUS DATOS</h1>
          <label for="floatingInput">Nombre</label>
          <div class="form-floating mb-3">
            <input
              minlength="5"
              type="text"
              class="form-control"
              id="floatingInput"
            />
          </div>

          <div class="form-floating mb-3">
            <label for="floatingInput">Telefono</label>
            <input type="text" class="form-control" id="floatingInput" />
          </div>
          <div class="form-floating">
            <label for="floatingPassword">Email</label>
            <input type="email" class="form-control" id="floatingInput" />
          </div>
          <div class="button">
            <div class="col-12">
              <b-button
                :pressed.sync="verification"
                type="button"
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
              </b-button>
            </div>
          </div>
        </div>
      </form>
      <div v-else>
        <h5 style="text-align: center">
          Gracias por comunicarse con nosotros. En breve un asistente se
          comunicara con usted
        </h5>
      </div>
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
@media (max-width: 1268px) {
  .data {
    float: left;
    width: 100%;
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
      verification: true,
      posts: null,
      slide: 0,
      sliding: null,
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
    onSlideStart(slide) {
      this.sliding = true;
    },
    onSlideEnd(slide) {
      this.sliding = false;
    },
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