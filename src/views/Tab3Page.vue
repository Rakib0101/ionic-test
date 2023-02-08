<template>
	<ion-page>
		<ion-header>
			<header-area />
		</ion-header>
		<ion-content :fullscreen="true">
			<ion-header collapse="condense">
				<ion-toolbar>
					<ion-title size="large">Tab 3</ion-title>
				</ion-toolbar>
			</ion-header>

			<ExploreContainer>
				<div class="px-6">
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
									<ion-card-title class="blog-title">{{
										item.title
									}}</ion-card-title>
								</ion-card-header>

								<ion-card-content class="p-0">
									{{ item.body }}
								</ion-card-content>
							</div>
						</ion-card>
					</div>
				</div>
			</ExploreContainer>
		</ion-content>
	</ion-page>
</template>

<script>
import axios from "axios";
import {
	IonPage,
	IonHeader,
	IonContent,
	IonToolbar,
	IonTitle,
	IonCard,
	IonCardContent,
	IonCardHeader,
	IonCardTitle,
} from "@ionic/vue";
import ExploreContainer from '@/components/ExploreContainer.vue';
import HeaderArea from "../components/HeaderArea.vue";

export default {
	components: {
		IonPage,
		IonHeader,
		IonContent,
		IonToolbar,
		IonTitle,
		IonCard,
		IonCardContent,
		IonCardHeader,
		IonCardTitle,
		HeaderArea,
		ExploreContainer
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
