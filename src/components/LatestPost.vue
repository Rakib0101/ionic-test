<template>
	<div>
		<div v-for="item in items" :key="item.id">
			<ion-card>
				<img alt="Silhouette of mountains" :src="item.image" />
				<ion-card-header>
					<ion-card-title>{{ item.title }}</ion-card-title>
				</ion-card-header>

				<ion-card-content>
					{{ item.content }}
				</ion-card-content>
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
		axios.get("http://localhost:8000/api/posts")
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
