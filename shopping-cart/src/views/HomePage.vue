<script setup>
import { ref } from 'vue';

const cartVisible = ref(false);

const changeCartVisibility = () => {
  cartVisible.value = !cartVisible.value;
  console.log(cartVisible.value);
}
</script>

<template>
  <div class="home"> 
    <h1>
      Shopping Cart
    </h1>
    <button class="btn success">
      Add to Cart
    </button>
    <button class="btn error ml-1">
      Clear Cart
    </button>
    <button class="btn error ml-1" 
    @click="changeCartVisibility"
    > 
      Open Cart 
    </button>
</div>
</template>

<style lang="scss" scoped>  
.ml-1{
    margin-left: 1rem;
}
/* Estilo para botão primário */
.btn.primary {
    background-color: #007bff;
    color: #fff;
    border: 1px solid #007bff;
}

/* Estilo para botão de sucesso */
.btn.success {
    background-color: #28a745;
    color: #fff;
    border: 1px solid #42077a;
}

/* Estilo para botão de erro */
.btn.error {
    background-color: #dc3545;
    color: #fff;
    border


/* Reset CSS para garantir uma base consistente */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Estilos globais para o corpo do documento */
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    color: #333;
    line-height: 1.6;
}

/* Estilo para a barra de navegação */
.navbar {
    background-color: #333;
    color: #fff;
    padding: 1rem;
}

.navbar a {
    color: #fff;
    text-decoration: none;
    margin-right: 1rem;
}

/* Estilo para os botões */
.btn {
    display: inline-block;
    background-color: #007bff;
    color: #fff;
    padding: 0.5rem 1rem;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    transition: background-color 0.3s ease;
}

.btn:hover {
    background-color: #0056b3;
}

/* Estilo para os cartões */
.card {
    background-color: #fff;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 5px;
    padding: 1rem;
    margin-bottom: 1rem;
}

.card h2 {
    margin-bottom: 0.5rem;
}

.card p {
    margin-bottom: 1rem;
}

/* Estilo para o rodapé */
.footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1rem;
}
}
</style>