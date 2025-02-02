<template>
    <div class="product-card">
      <img :src="product.thumbnail" :alt="product.name" />
      <h3>{{ product.name }}</h3>
      <p>{{ product.price }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProductCard",
    props: {
      product: Object
    },
    methods: {
      addToCart() {
        alert(`${this.product.name} added to cart.`);
      }
    }
  };
  </script>
  
  <style scoped>
  .product-card {
    width: 200px;
    padding: 10px;
    border: 1px solid #ccc;
    text-align: center;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  }
  
  .product-card img {
    width: 100%;
    height: 150px;
    object-fit: cover;
  }
  
  .product-card button {
    margin-top: 10px;
    padding: 5px 10px;
    cursor: pointer;
    background-color: #007bff;
    color: white;
    border: none;
  }
  
  .product-card button:hover {
    background-color: #0056b3;
  }
  </style>
  