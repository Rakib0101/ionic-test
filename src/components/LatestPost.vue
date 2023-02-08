<template>
	<div>
		<div v-for="item in items" :key="item.id">
			<ion-card class="blog-card">
				<div class="img">
					<img
						alt="Silhouette of mountains"
						src="https://fastly.picsum.photos/id/866/200/300.jpg?hmac=rcadCENKh4rD6MAp6V_ma-AyWv641M4iiOpe1RyFHeI"
					/>
				</div>
				<div class="content">
					<ion-card-header class="p-0">
						<p class="published-date">24 Jan, 2022</p>
						<ion-card-title class="blog-title">{{ item.title }}</ion-card-title>
					</ion-card-header>

					<ion-card-content class="p-0">
						{{ item.body }}
					</ion-card-content>
				</div>
			</ion-card>
		</div>
	</div>
</template>

<script>
import axios from "axios";
import {
	IonCard,
	IonCardContent,
	IonCardHeader,
	IonCardTitle,
} from "@ionic/vue";

export default {
	components: {
		IonCard,
		IonCardContent,
		IonCardHeader,
		IonCardTitle,
	},
	data() {
		return {
			items: [],
			loading: true,
		};
	},
	mounted() {
		axios
			.get("https://jsonplaceholder.typicode.com/posts")
			.then((response) => {
				this.items = response.data;
				console.log(this.items);
				this.loading = false;
			})
			.catch((e) => {
				console.log(e);
			});
	},
};
</script>
<style>
.blog-card{
	display: flex;
	gap: 16px;
	align-items: start;
	margin: 24px 0px;
	padding-bottom: 24px;
	border-bottom: 1px solid #ddd;
	box-shadow: none;
}
.blog-card .img{
	width: 74px;
	height: 74px;
}
.blog-card .img img{
	width: 74px !important;
	height:74px !important;
}
.blog-card .content{
	width: 100%;
}
.blog-card .content .published-date{
	margin-top: 0px;
	margin-bottom: 5px;
}
.blog-card .blog-title{
	font-family: 'Inter';
	font-style: normal;
	font-weight: 600;
	font-size: 16px;
	line-height: 24px;
	color: #101828;
	margin-top: 0px;
	margin-bottom: 5px;
}
.p-0{
	padding: 0px;
}
</style>
