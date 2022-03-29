<template>
    <div>
        <h2>Checkout</h2>
        <h3>Added products</h3>
        <div v-for='product in cart' :key="product.id">
        {{product.title}} 
        <button @click="removeProduct">remove</button>
    </div>
        <p>
                        <strong>First Name</strong>
                        <input v-model.trim = 'order.firstName'>
                    </p>
                    <p>
                        <strong>Last Name</strong>
                        <input v-model = 'order.lastName'>
                    </p>
                    <p>
                        <strong>Address:</strong>
                        <input v-model = 'order.address'>
                    </p>
                    <p>
                        <strong>City:</strong>
                        <input v-model = 'order.city'>
                    </p>
                    <p>
                        <strong>State</strong>
                        <select v-model = 'order.state'>
                            <option disabled value = "">State</option>
                            <option>{{state}}</option>
                        </select>  
                    </p>
                    <p>
                        <strong>Zip/Postal code: </strong>
                        <input v-model.number = 'order.zip'>
                    </p>
                    <p>
                        <input type= "checkbox" id = 'gift' v-model = 'order.gift' :true-value = 'order.sendGift' :false-value = 'order.dontSendGift'>
                        <label for = "gift">Ship as a gift?</label>
                    </p>
                    <p>
                        <input type = "radio" id = 'home' value = 'h' v-model = 'order.method'>
                        <label for = "home">Home</label>
                        <input type = "radio" id = 'business' value = 'b' v-model = 'order.method'>
                        <label for = "business">Business</label>
                    </p>

                    <h2>Order Information</h2>
                    <p>FirstName: {{order.firstName}}</p>
                    <p>LastName: {{order.lastName}}</p>
                    <p>Address: {{order.address}}</p>
                    <p>City: {{order.city}}</p>
                    <p>Zip: {{order.zip}}</p>
                    <P>State: {{order.state}}</P>
                    <p>Ship as a gift? {{order.gift}}</p>

                    <button @click = 'submitForm'>Submit Order</button>
    </div>
</template>

<script>
export default{
    name:"checkout",
    props:['cart'],
    data(){
        return{
            name:"",
            address:"",
        }
    },
    methods:{
        removeProduct(product){
            this.$emit('removeProduct',product)
        }
    }
};
</script>
