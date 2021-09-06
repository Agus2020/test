<template>
  <div class="footer">
    <div class="pie py-1">
      <div class="row p-3" >
        <h4>Nissan. Innovation that excites.</h4>
        <div class="col-3 p-3">
          <h6>COTIZACIÓN DE VEHÍCULOS</h6>
          <ul class="nav flex-column">
            <li class="nav-item mb-2">
              <a href="#" class="nav-link p-0 text-muted"
                ><p style="color: white">Información Legal</p></a
              >
            </li>
          </ul>
        </div>
        <div class="col-2 p-3">
          <h6>RALITOR S.A.</h6>
          <br />
          <ul class="nav flex-column">
            <li class="nav-item mb-2">
              <a href="#" class="nav-link p-0 text-muted"
                ><p style="color: white">nissan.com.uy</p></a
              >
            </li>
            <br />
            <li class="nav-item mb-2">
              <a href="#" class="nav-link p-0 text-muted"
                ><p style="color: white">Políticas de Cookies</p></a
              >
            </li>
          </ul>
        </div>

        <div class="col-2 p-3">
          <h6>AYUDA AL CLIENTE</h6>
          <ul class="nav flex-column">
            <li class="nav-item mb-2">
              <a href="#" class="nav-link p-0 text-muted" style="color: white"
                ><p style="color: white">Políticas de Privacidad</p></a
              >
            </li>
          </ul>
        </div>

        <div class="col-4 offset-1 p-3">
          <form class="form">
            <h6>NISSAN SOCIAL</h6>
            <div class="d-flex w-100 gap-2">
              <a href="https://www.facebook.com/nissanuruguay"
                ><img src="../static/f.svg" class="p-1"
              /></a>
              <a href="https://www.instagram.com/nissanuruguay/"
                ><img src="../static/i.svg" class="p-1"
              /></a>
              <a href="https://twitter.com/uruguaynissan"
                ><img src="../static/t.svg" class="p-1"
              /></a>
              <a href="https://www.youtube.com/channel/UCvQjL7hfaO3ICXjlgSm3alg"
                ><img src="../static/y.svg" class="p-1"
              /></a>
            </div>
          </form>
        </div>
      </div>

      <div class="d-flex justify-content-between py-4 my-4 border-top">
        <div class="derechos">
          <p>© 2020 SIMPLICAR. Todos los derechos reservados.</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Footer",
};
</script>
