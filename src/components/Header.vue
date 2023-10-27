<script setup lang="ts">
import { useRoute } from "vue-router";
const location = useRoute();
import { useAuthStore } from "@/stores/index";
const authStore = useAuthStore();
</script>


<template>
  <nav class="navbar navbar-expand-lg fixed-top">
<div class="nabvars">
      <RouterLink to="/" class="navbar-brand">
        <lord-icon
          src="../src/assets/json/config.json"
          trigger="loop"
          state="loop-cog"
          colors="primary:#fff"
          style="width:40px;height:40px">
      </lord-icon>
      </RouterLink>
      <RouterLink v-if="!authStore.token" to="/login" class="btn custom-btn d-lg-none ms-auto me-4">
        Iniciar Sesión
      </RouterLink>

      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
        aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav align-items-lg-center ms-auto me-lg-5">

          <li class="nav-item">
            <RouterLink to="/ayuda">
              <lord-icon
    src="https://cdn.lordicon.com/ojnjgkun.json"
    trigger="hover"
    colors="primary:#ffffff"
    style="width:50px;height:50px">
</lord-icon>
            </RouterLink>
            &nbsp;&nbsp;
          </li>
          <li class="nav-item">
            <RouterLink v-if="authStore.token" to="/catproducto">
              Categoría</RouterLink>
          </li>
          &nbsp;&nbsp;
          <li class="nav-item">
            <RouterLink v-if="authStore.token" to="/producto">Productos
            </RouterLink>
          </li>

        </ul>
        <RouterLink v-if="!authStore.token" to="/login" class="">
          <lord-icon
            src="../src/assets/json/login.json"
            trigger="hover"
            colors="primary:#fff"
            style="width:40px;height:40px">
        </lord-icon>
        </RouterLink>
        <a v-else @click="authStore.logout()" class="btn btn-danger">
          Cerrar Sesión
        </a>
      </div>
    </div>
  </nav>
</template>
<style>
.smaller-image {
  width: 100px;
  /* Ajusta el ancho según tus necesidades */
  height: auto;
  /* Ajusta la altura proporcionalmente */
}
.nabvars {
  background-color: rgba(0, 145, 255, 0.722);
  width: 100%;
  display: flex;
  justify-content: space-between; 
  align-items: center;
  border-radius: 10px; 
  padding-left: 5%; 
  padding-right: 5%;
  padding-top: 1px;
  padding-bottom: 1px;
  border: 2px solid #007890; 

}



</style>
