<template>
    <div>
        
        <h1>products</h1>

        <div class="products">
            <div v-for="(product) in products" :key="product.name">
            {{ product.name }}
            <img :src="product.image">
            {{ product.cost }}
            <button @click="addItemToCart(product)">add to cart</button>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    data:() => {
        return {
                products: [
            {
                name: "hair brush",
                cost: "$0.99",
                image: "https://i.pinimg.com/736x/52/e2/12/52e212f9c794394126f9babf9a2c6b37.jpg",
            },
            {
                name: "cookies",
                cost: "$0.9",
                image: "https://i.pinimg.com/736x/e8/b0/ad/e8b0ad5733dd9b153e13b8e99df967fd.jpg",
            },
            {
                name: "Shirt",
                cost: "$10.99",
                image: "https://i.pinimg.com/736x/83/30/bf/8330bf86093ba55753b7a33470c3447d.jpg",
            }
            ]
        };
    },
        methods: {
            addItemToCart(product) {
                this.$emit('addItemToCart', product)
            }
        },
    };
</script>


<style scoped>

</style>