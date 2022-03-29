<template>
    <div id="app">
        <header>
            <h1>{{sitename}}</h1>
            <button @click="showCheckout">{{this.cart.length}} Check out</button>
        </header>
        <product-list @addProduct='addToCart'></product-list>
        <checkout :cart='cart' @removeProduct='removeFromCart'></checkout>
    </div>
</template>

<script>
import Productlist from './productlist.vue'
import Checkout from './checkout.vue'

export default{
    name:'app',
    components:{
        Productlist, Checkout,
    },
    data(){
        return{
            sitename:'Lesson Store',
            cart:[],
        };
    },
    methods:{
        showCheckout(){},
        addToCart(product){this.cart.push(product)
        product.inventory  --},
        removeFromCart (product){
            this.cart.forEach(product2 =>{
                if(product2.id === product.id){
                    product.inventory ++
                    this.cart.splice(this.cart.index(product),1)
                }
            });
        }
    }
}
</script>

<style>
#app{
    font-family: Avenir,Arial, Helvetica, sans-serif;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    text-align: center;
    color:#2c3e50;
    margin-top: 60px;
}
</style>
