<template>
	<ion-page>
		<ion-header>
			<header-area />
			<!-- <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar> -->
		</ion-header>
		<ion-content :fullscreen="true">
			<ion-header collapse="condense">
				<ion-toolbar>
					<ion-title size="large">Tab 3</ion-title>
				</ion-toolbar>
			</ion-header>

			<ExploreContainer>
				<ion-card>
					<img alt="Silhouette of mountains" :src="item.image" />
					<ion-card-header>
						<ion-card-title>Post Title</ion-card-title>
					</ion-card-header>

					<ion-card-content>
						Lorem ipsum dolor sit, amet consectetur adipisicing
						elit. Voluptatibus fugiat dicta omnis corporis alias, et
						libero quas ipsam perspiciatis esse?
					</ion-card-content>
				</ion-card>
			</ExploreContainer>
		</ion-content>
	</ion-page>
</template>

<script setup lang="ts">
import {
	IonPage,
	IonHeader,
	IonToolbar,
	IonTitle,
	IonContent,
  IonCard,
  IonCardHeader,
  IonCardTitle,
  IonCardContent
} from "@ionic/vue";
import ExploreContainer from "@/components/ExploreContainer.vue";
import HeaderArea from "../components/HeaderArea.vue";
</script>
