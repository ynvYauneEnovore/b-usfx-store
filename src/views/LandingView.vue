<script setup lang="ts">
import Header from "@/components/Header.vue";
import DefaultFooter from "@/components/Footer.vue";
</script>

<template>
 

  <Header />

  <div class="gallery">
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 1">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 2">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 3">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 4">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 5">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 6">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 7">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 8">
        </div>
        <div class="image">
            <img src="@/assets/images/food-beverage-1.jpg" alt="Imagen 9">
        </div>
    </div>

  
  <div class="menu-lado">

    <h1>Filtro de Productos</h1>
        <form id="filtro-tienda">
            <label for="categoria">Categoría:</label>
            <select id="categoria" name="categoria">
                <option value="todos">Todos</option>
                <option value="ropa">Ropa</option>
                <option value="electronicos">Electrónicos</option>
                <option value="hogar">Hogar</option>
            </select>

            <label for="precio-min">Precio Mínimo:</label>
            <input type="number" id="precio-min" name="precio-min" min="0" step="1">
            
            <label for="precio-max">Precio Máximo:</label>
            <input type="number" id="precio-max" name="precio-max" min="0" step="1">
            
            <input type="submit" value="Filtrar">
        </form>
</div>
  <DefaultFooter />
</template>

<style>

.menu-lado {

  padding: 5px;
  background-color: lightgreen;
  overflow: auto;
  position: fixed;
  top: 19%;
  left: 1%;
  right: 89%;
  width: 350px;
  z-index: 1;

  
}

h1 {
            color: #333;
        }

        label {
            display: block;
            margin-top: 10px;
        }

        select, input[type="number"], input[type="submit"] {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 16px;
        }

        input[type="submit"] {
            background-color: #007BFF;
            color: #fff;
            cursor: pointer;
        }


        .gallery {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            max-width: 90%;
            padding-left: 40%;
            padding-top: 7%;

        }

        .image {
            position: relative;
            overflow: hidden;
            border: 2px solid #fff;
            box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s;
        }

        .image:hover {
            transform: scale(1.05);
        }

</style>


