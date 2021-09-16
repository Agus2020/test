<template>
  <div v-if="post">
    <div class="card mb-5 p-1 pb-2 autoid">
      <div>
        <b-carousel
          id="carousel-1"
          v-model="slide"
          controls
          indicators
          background="gray"
          :interval="5000"
          img-width="1200"
          img-height="480"
          @sliding-start="onSlideStart"
          @sliding-end="onSlideEnd"
        >
          <div class="carouselid">
            <b-carousel-slide
              v-for="item in post.gallery"
              :key="item.id"
              :img-src="
                'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +
                item.large
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
              <ul class="list-group list-group-flash uldescripcionid">
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

    
    <div class="data p-5 m-5 col-5 formid">
      <form class="dat" v-if="verification">
        <div>
          <h1 class="text-center">INGRESÁ TUS DATOS</h1>
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
          <div class="col-12">
            <b-button
              :pressed.sync="verification"
              type="button"
              class="btn btn-primary m-5 buttonid"
            >
              ENVIARME LA COTIZACIÓN POR MAIL
            </b-button>
          </div>
        </div>
      </form>
      <div v-else>
        <h5 class="text-center">
          Gracias por comunicarse con nosotros. En breve un asistente se
          comunicara con usted
        </h5>
      </div>
    </div>
  </div>
</template>


<style>
.carouselid{
  opacity: 0.9
}
.formid {
  float: left;
}
.buttonid {
  color: black;
}
.autoid {
  float: left;
  width: 600px;
}
.buttonid {
  background: #af1c1c;
  height: 50px;
  font-size: 17px;
  width: 350px;
}
.uldescripcionid{
  width: 90%;
}
@media (max-width: 1193px) {
  .formid {
    width: 400px;
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