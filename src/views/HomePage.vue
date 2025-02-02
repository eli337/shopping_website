<template>
  <div>
    <h1>Welcome to Our Shopping Website</h1>

    <!-- Featured Categories Section -->
    <section class="categories">
      <h2>Featured Categories</h2>
      <div class="category-list">
        <div class="category-item">
          <img :src="require('@/assets/images/category1.png')" alt="Category 1" />
          <p>Category 1</p>
        </div>
        <div class="category-item">
          <img :src="require('@/assets/images/category2.png')" alt="Category 2" />
          <p>Category 2</p>
        </div>
      </div>
    </section>

    <!-- Products Section -->
    <section class="products">
      <h2>Normal Products</h2>
      <div class="product-list">
        <ProductCard 
          v-for="product in products" 
          :key="product.id" 
          :product="product" 
        />
      </div>

      <!-- Checkout Button -->
      <div class="checkout-section">
        <button @click="checkout">Checkout</button>
      </div>
    </section>

    <section class="specials">
      <h2>Special Products</h2>
      <div class="special-offer">
        <img :src="require('@/assets/images/special1.png')" alt="Special Offer 1" />
        <p>From $10</p>
        <button>Shop Now</button>
      </div>
    </section>
  </div>
</template>

<script>
// 引入 ProductCard 组件
import ProductCard from '@/components/ProductCard.vue';

export default {
  name: "HomePage",
  components: {
    ProductCard
  },
  data() {
    return {
      // 修改：通过 require() 引入本地图片
      products: [
        { 
          id: 1, 
          name: "Product 1", 
          price: "$10.0", 
          // 使用 require 引入图片路径
          thumbnail: require('@/assets/images/product1.png') 
        },
        { 
          id: 2, 
          name: "Product 2", 
          price: "$20.0", 
          // 使用 require 引入图片路径
          thumbnail: require('@/assets/images/product2.png') 
        }
      ]
    };
  },
  methods: {
    // 结账按钮的功能
    checkout() {
      alert("Proceeding to checkout...");
    }
  }
};
</script>

<style scoped>
h1 {
  color: #42b983;
  text-align: center;
}

.categories {
  margin-top: 40px;
  text-align: center;
}

.category-list {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.category-item {
  text-align: center;
  width: 200px;
}

.category-item img {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

.products {
  margin-top: 40px;
  text-align: center;
}

.product-list {
  display: flex;
  /* justify-content: flex-start; */
  justify-content: space-evenly;
  gap: 20px;
  flex-wrap: wrap;
}

.checkout-section {
  position: fixed; 
  bottom: 20px; 
  right: 20px; 
  text-align: center;
}

.checkout-section button {
  padding: 10px 20px;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.checkout-section button:hover {
  background-color: #34a768;
}

.specials {
  margin-top: 40px;
  text-align: center;
}

.special-offer {
  display: inline-block;
  width: 300px;
  padding: 20px;
  border: 1px solid #ccc;
  text-align: center;
}

.special-offer img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.special-offer button {
  margin-top: 10px;
  padding: 10px 20px;
  cursor: pointer;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
}

.special-offer button:hover {
  background-color: #0056b3;
}

/* 添加响应式布局 */
@media (max-width: 768px) {
  .category-list {
    flex-direction: column;
    align-items: center;
  }

  .product-list {
    flex-direction: column;
    align-items: center;
  }
}
</style>
