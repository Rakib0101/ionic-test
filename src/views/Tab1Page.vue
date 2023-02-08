<template>
	<ion-page>
		<ion-header>
			<header-area />
			<!-- <ion-toolbar>
				<ion-title>Tab 1</ion-title>
			</ion-toolbar> -->
		</ion-header>
		<ion-content :fullscreen="true">
			<ion-header collapse="condense">
				<ion-toolbar>
					<ion-title size="large">Tab 1</ion-title>
				</ion-toolbar>
			</ion-header>

			<explore-container class="container">
				<div class="tab-buttons">
					<button
						@click="selectedTab = 'tab1'"
						class="tab-btn"
						:class="{ active: selectedTab === 'tab1' }"
					>
						Latest Post
					</button>
					<button
						@click="selectedTab = 'tab2'"
						class="tab-btn"
						:class="{ active: selectedTab === 'tab2' }"
					>
						Trending
					</button>
					<button
						@click="selectedTab = 'tab3'"
						class="tab-btn"
						:class="{ active: selectedTab === 'tab3' }"
					>
						Popular
					</button>
				</div>
				<div v-if="selectedTab === 'tab1'">
					<latest-post />
				</div>
				<div v-if="selectedTab === 'tab2'">
					<trending-post />
				</div>
				<div v-if="selectedTab === 'tab3'">
					<popular-post />
				</div>
			</explore-container>
		</ion-content>
	</ion-page>
</template>

<script>
import {
	IonPage,
	IonHeader,
	IonToolbar,
	IonTitle,
	IonContent,
} from "@ionic/vue";
import ExploreContainer from "@/components/ExploreContainer.vue";
import HeaderArea from "../components/HeaderArea.vue";
import LatestPost from "../components/LatestPost.vue";
import TrendingPost from "../components/TrendingPost.vue";
import PopularPost from "../components/PopularPost.vue";
export default {
	components: {
		HeaderArea,
		ExploreContainer,
		IonPage,
		IonHeader,
		IonToolbar,
		IonTitle,
		IonContent,
		TrendingPost,
		PopularPost,
		LatestPost
	},
	data() {
		return {
			selectedTab: "tab1",
		};
	},
};
</script>
<style>
ion-header{
	position: static;
}
.container{
	padding: 0px 24px;
}
.tab-buttons{
	display: flex;
	gap: 24px;
}
.tab-buttons .tab-btn{
	color: #98A2B3;
	padding-bottom: 8px;
	border-bottom: 2px solid transparent;
	background: transparent;
	font-family: 'Inter';
	font-style: normal;
	font-weight: 600;
	font-size: 16px;
	line-height: 24px;
}
.tab-buttons .tab-btn.active{
	color: #6941C6;
	border-bottom: 2px solid #6941C6;
}
</style>
