<template>
    <div class="product-page">
      <h1>{{ product.name }}</h1>
      <img :src="product.fullSizeImage" alt="Product Full Image" />
      <p>{{ product.description }}</p>
      <p>{{ product.price }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProductPage",
    data() {
      return {
        product: {
          id: 1,
          name: "Product 1",
          price: "$10.0",
          description: "This is a description for Product 1.",
          fullSizeImage: "product1_full.jpg"
        }
      };
    },
    methods: {
      addToCart() {
        console.log(`${this.product.name} added to cart.`);
      }
    }
  };
  </script>
  
  <style scoped>
  .product-page {
    text-align: center;
  }
  
  .product-page img {
    width: 300px;
    height: auto;
  }
  
  .product-page button {
    margin-top: 10px;
    padding: 5px 10px;
    cursor: pointer;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 4px;
  }
  
  .product-page button:hover {
    background-color: #0056b3;
  }
  </style>
  