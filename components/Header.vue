<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <nuxt-link to="/">
      <a class="navbar-brand" href="#"><img src="../static/Logo.png" /></a>
    </nuxt-link>
    <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
        <li class="nav-item active">
          <nuxt-link to="/posts">
            <a class="nav-link">VEHICULOS</a>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/posts">
            <a class="nav-link">DESCUBRI NISSAN</a>
          </nuxt-link>
        </li>
      </ul>
      <form class="form">
        <input
          class="form-control mr-sm-2"
          type="search"
          placeholder="Search"
          aria-label="Search"
        />
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit">
          Search
        </button>
      </form>
    </div>
  </nav>
</template>
<script>
export default {
  name: "Header",
};
</script>