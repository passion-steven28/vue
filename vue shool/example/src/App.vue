<template>
  <div id="app">

    <header>
      <button @click="navigateTo('products')">view products</button>
      {{ cart.length }}to cart  
      <button @click="navigateTo('cart')">view cart</button>
    </header>

    <div v-if="page === 'cart'">

      <cart v-on:removeItemToCart="removeItemToCart" :cart="cart"/>

    </div>

    <div v-if="page === 'products'">

      <products v-on:addItemToCart="addItemToCart"/>

    </div>

  </div>
</template>

<script>
import products from './components/products.vue';
import cart from "./components/cart.vue";

  export default {
    name: "app",
    data: () => {
      return {
        page: "products",
        cart: [],
        
      };
    },
    methods: {
      addItemToCart(product){
        console.log(product);
        this.cart.push(product);
      },
      removeItemToCart(index) {
        this.cart.splice(index, 1);
      },
      navigateTo(page) {
        this.page = page;
      }
    },
    components: { products,cart }
  };
</script>


<style>
  .products{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    height: 70vh;
    padding: auto;
    gap: 1rem;
  }
  img{
    display: block;
    width: 100%;
    /* height: 100%; */
    object-fit: contain;
    border-radius: 8px;
    cursor: pointer;
    margin-bottom: 10px;
  }

  header{
    background-color: #750e94;
    padding: 1rem;
    border-radius: 8px;
  }
</style>