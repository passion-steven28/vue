<template>
    <div>
        
        <h1>your cart</h1>

        <div class="products">
            <div v-for="(product, index) in cart" :key="product.name">
            {{ product.name }}
            <img :src="product.image">
            {{ product.cost }}
            <button @click="removeItemToCart(index)">remove to cart</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ["cart"],
    methods: {
        removeItemToCart(product) {
            this.$emit('removeItemToCart', product);
        }
    }
}
</script>

<style>

</style>
