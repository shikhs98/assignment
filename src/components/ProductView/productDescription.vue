<template>
		<div class="row" style="margin:10px">
			<div class="col-md-5" style="background-color:#D3D3D3;padding:20px;">
				<pricingDetails :productList="productList"/>
			</div>
			<div class="col-md-7" style="background-color:#D3D3D3;">
				<imageDescription @updateProductList="updateProductList"/>
			</div>
		</div>
</template>
<script>
	import imageDescription from "@/components/ProductView/imageDescription";
	import pricingDetails from "@/components/ProductView/pricingDetails";
	export default {
		name: "productDescription",
		components: {
			imageDescription,
			pricingDetails
		},
		data(){
			return{
				productList:{}
			}
		},
		methods:{
			updateProductList(product){
				console.log('hhuihu')
				if(!this.productList[product.name]){
					this.productList[product.name] = product
				}
				else{
					product.quantity ++;
					this.productList[product.name] = product
				}
				this.productList = JSON.parse(JSON.stringify(this.productList))
			}
		}
	};
</script>

