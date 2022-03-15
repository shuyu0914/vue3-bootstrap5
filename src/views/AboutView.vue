<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Navbar />

    <div class="row mt-3">
		  <div class="col-sm-6 col-xs-12" v-for="card in cardList">
		    <div class="card">
		      <div class="card-body">
		        <h5 class="card-title">{{card.name}}</h5>
		        <p class="card-text">{{card.success}}</p>
		      </div>
		    </div>
		  </div>
		</div>

  </div>
</template>

<script>
import {ref,reactive} from 'vue'
import Navbar from '@/components/Navbar'
export default{
	name: 'AboutView',
	components:{Navbar},
	setup(){
		const cardList = reactive([])

		const getCardData = () => {
			let sample_data1 = {name:'vue3-boostrap5',success:true}
			let sample_data2 = {name:'vue3-vuetify-no-rc',success:false}
			cardList.push(sample_data1)
			cardList.push(sample_data2)
			console.log("cardList = ",cardList)
		}

		getCardData()

		return {cardList} //回傳頁面view需要的東西
	}
}
</script>