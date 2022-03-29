<template>
    <main>
        <div v-for="product in products" :key="product.id">
            <h2>{{product.title}}</h2>
            <figure>
                <img v-bind:src="product.image" />
                </figure> 
                <p>Description:{{product.description}}</p>
                <p>Price: {{ product.price }}</p>
                <p>Available stock: {{ product.inventory }}</p>
                <button @click="addToCart(product)">Add to cart</button>
                </div>
            </main>
</template>

<script>
export default{
    name:"ProductList",
    data(){
        return{
            products:[
                {
	id:1001,
	title:"Maths",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 3
	},
	{
	id:1002,
	title:"Chinese",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 2	
	},
	{
	id:1003,
	title:"French",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 4	
	},
	{
	id:1004,
	title:"C++",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 1	
	},
	{
	id:1005,
	title:"C",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 5	
	},
	{
	id:1006,
	title:"Java Script",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 2	
	},
	{
	id:1007,
	title:"HTML5",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 4	
	},
	{
	id:1008,
	title:"VUE",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 1	
	},
	{
	id:1009,
	title:"Computer Graphic",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 3	
	},
	{
	id:1010,
	title:"Dance",
	location:"London",
	price:2000,
	image:"product-fullsize.png",
	availableInventory: 5,
	rating: 5	
	},
            ]
        }
    },
    methods:{
        addtoCart(product) {
            this.$emit('addProduct',product)
        }
    }
}
</script>
