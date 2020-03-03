<template>
<div>
    <div class="row">
        <div class="col-md-4" style="text-align: left;;background-color:#D3D3D3">SubTotal</div>
        <div class="col-md-8" style="background-color:white">
            <span style="float:left">{{subTotal}} EUR</span>
            <span style="float:right">{{items}} items</span>
        </div>
    </div>
    <div class="row">
        <div class="col-md-4" style="text-align: left;;background-color:#D3D3D3">Vat Tax</div>
        <div class="col-md-8" style="background-color:white">
            <input type=number style="float:left;border:none" v-model="vatTax"/>
            <span style="float:right">{{vatTax?vatTax*100/subTotal:0}} EUR</span>
        </div>
    </div>
    <div class="row">
        <div class="col-md-4" style="text-align: left;;background-color:#D3D3D3">Discount</div>
        <div class="col-md-8" style="background-color:white">
            <input type=number style="float:left;border:none" v-model="discount"/>
            <span style="float:right">{{discount?discount*100/subTotal:0}} EUR</span>
        </div>
    </div>
    <div class="row">
        <div class="col-md-4" style="text-align: left;;background-color:#D3D3D3">Total</div>
        <div class="col-md-8" style="background-color:white">
            <span style="float:left;color:green" >{{total}} EUR</span>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "priceCalculator",
    data(){
        return{
            subTotal:0,
            items:0,
            vatTax:0,
            discount:0,
            total:0
        }
    },
    watch:{

    }
}
</script>

<style>

</style>
