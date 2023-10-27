<template>
    <div class="login-container">
      <form @submit.prevent="onSubmit" class="login-form">
        <div class="text-center">
        <RouterLink to="/">
            <lord-icon
            src="../src/assets/json/home.json"
            trigger="hover"
            colors="primary:#007BFF"
            style="width:100px;height:100px">
            </lord-icon>
        </RouterLink>
        </div>

        <h2 class="login-title">Acceder</h2>
  
        <div class="form-group">
          <label for="usuario">Usuario:</label>
          <input type="text" id="usuario" v-model="usuario" required class="form-control">
        </div>
  
        <div class="form-group">
          <label for="clave">Contraseña:</label>
          <input type="password" id="clave" v-model="clave" required class="form-control">
        </div>
  
        <button type="submit" class="login-button">Ingresar</button>
  
        <p v-if="error" class="error-message">Usuario y/o contraseña incorrectos</p>
      </form>
    </div>
  </template>
  
  <script>
  import { ref } from "vue";
  import { useAuthStore } from "@/stores/index";
  
  export default {
    setup() {
      const usuario = ref("admin@admin.com");
      const clave = ref("12345678");
      const error = ref(false);
  
      const onSubmit = () => {
        const authStore = useAuthStore();
        authStore.login(usuario.value, clave.value).catch(() => (error.value = true));
      };
  
      return {
        usuario,
        clave,
        error,
        onSubmit
      };
    }
  }
  </script>
  
  <style scoped>
  .login-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #f4f4f4;
  }
  
  .login-form {
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
    padding: 20px;
    width: 300px;
    transition: transform 0.2s ease;
  }
  
  .login-form:hover {
    transform: scale(1.05);
  }
  
  .login-title {
    font-size: 24px;
    text-align: center;
    margin-bottom: 20px;
  }
  
  .form-group {
    margin: 10px 0;
  }
  
  .form-control {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  .login-button {
    background: #007BFF;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    width: 100%;
    transition: background 0.3s;
  }
  
  .login-button:hover {
    background: #0056b3;
  }
  
  .error-message {
    color: red;
    text-align: center;
  }
  </style>
  