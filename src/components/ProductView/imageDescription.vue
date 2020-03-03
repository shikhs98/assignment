<template>
<div>
	<div class="row"  style="padding:10px">
		<div class="col-md-2 card text-white" v-for= "(item,index) in prodImages" :key="index" style="margin-top:20px;margin-bottom:20px;margin-left:20px;height:180px;border-radius:10px;padding:0px">
			<img @mouseenter="showDetails(index)" @mouseleave="hideDetails(index)" @click="addProduct(index)" class ="card-img" style="height:178px" src="
            data:image/jpeg;base64,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 " alt="Card image">
			<div @mouseenter="showDetails(index)" @mouseleave="hideDetails(index)" @click="addProduct(index)" style="position:absolute;left:0px;right:0px">
				<h5 style="margin-top:20px">{{item.name}}</h5>
				<h5 v-show="index===showPrice">{{item.price}}</h5>
                <span v-show="index===showPrice">{{item.description}}</span>
			</div>
		</div>
	</div>
</div>
</template>
<script>
	export default {
		name: "imageDescription",
		data() {
			return {
                showPrice:'',
				prodImages: [
					{
						name: "comuter",
						price: "130",
						category: "computers",
						description: "",
						image: "comuter.jpg"
					},
					{
						name: "sweater",
						price: "1",
						category: "Clothing",
						description: "fashion, clothes , sweater, wool, cardigan,…"
                    },
					{
						name: "tie",
						price: "46",
						category: "Clothing",
						description:
							"fashion, tie, clothes, accessory , accessoire,…",
						image: "tie.jpeg"
					},
					{
						name: "jacket men",
						price: "225",
						category: "Clothing",
						description: "fashion  man  jacket ",
						image: "jacket_men.jpg"
					},
					{
						name: "mouse",
						price: "80",
						category: "computers",
						description: "apple   mouse  ",
						image: "mouse.jpg"
					}
				]
			};
        },
        methods:{
            addProduct(index){
                var product = this.prodImages[index]
                product['quantity'] = 1
                this.$emit('updateProductList',product)
                console.log(index)                
            },
            showDetails(index){
                this.showPrice = index
            },
            hideDetails(){
                this.showPrice = ''
            }
        }
	};
</script>

    
