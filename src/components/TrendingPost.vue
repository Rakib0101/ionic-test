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

