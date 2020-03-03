<template>
<div>
    <div class="row" style="padding:10px">
        <div class="col-md-1"></div>
        <div class="col-md-3">Products</div>
        <div class="col-md-2">Price</div>
        <div class="col-md-3">Quantity</div>
        <div class="col-md-3">Total</div>
    </div>
    <div v-if="!(Object.keys(productList||{}).length)">
        <NoProduct/>
    </div>
    <div style="padding:15px">
        <PriceCalculations/>
    </div>
</div>
</template>
<script>
import NoProduct from "@/components/ProductView/NoProduct.vue"
import PriceCalculations from "@/components/ProductView/PriceCalculator.vue"
export default {
    name:'pricingDetail',
    components:{
        NoProduct,
        PriceCalculations
    },
    data(){
        return{
            productsAdded:[]
        }
    },
    props:{
     productList:{
         type:Object
     }},
    mounted(){
        console.log(JSON.stringify(this.productList)+'ko')
    }
}
</script>

    
