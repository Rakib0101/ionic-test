<template>
  <ion-page>
    <ion-header>
      <header-area />
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 2</ion-title>
        </ion-toolbar>
      </ion-header>

      <ExploreContainer>
        <div class="px-6">
          <ion-searchbar placeholder="Custom Placeholder"></ion-searchbar>
        </div>
        <div class="tags-wrap">
          <h2>Popular Tags</h2>
          <ul>
            <li>
              <a href="#">Solar panel</a>
            </li>
            <li>
              <a href="#">Temperature</a>
            </li>
            <li>
              <a href="#">Light-year</a>
            </li>
            <li>
              <a href="#">Electricity</a>
            </li>
            <li>
              <a href="#">Crude oil</a>
            </li>
            <li>
              <a href="#">Binary star</a>
            </li>
            <li>
              <a href="#">Density</a>
            </li>
            <li>
              <a href="#">Robotics</a>
            </li>
            <li>
              <a href="#">Turbine</a>
            </li>
            <li>
              <a href="#">Evolution</a>
            </li>
            <li>
              <a href="#">Interstellar</a>
            </li>
            <li>
              <a href="#">Mineral</a>
            </li>
            <li>
              <a href="#">Carbon footprint</a>
            </li>
            <li>
              <a href="#">Gibbous moon</a>
            </li>
          </ul>
        </div>
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
import { IonPage, IonHeader, IonSearchbar, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';
import HeaderArea from "../components/HeaderArea.vue";

export default {
  components:{
    IonPage, IonHeader, IonSearchbar, IonToolbar, IonTitle, IonContent, ExploreContainer, HeaderArea
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
}
</script>
<style>
.tags-wrap{
  padding: 0px 24px;
}
.tags-wrap h2{
  font-family: 'Inter';
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 18px;
  color: #000000;
}
.tags-wrap ul {
  list-style: none;
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  padding: 0px;
  margin: 0px;
}
.tags-wrap ul li a{
  padding: 2px 8px;
  background: #F2F4F7;
  border-radius: 16px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  font-family: 'Inter';
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 18px;
  text-align: center;
  color: #344054;
  text-decoration: none;
}
.px-6{
  padding-left: 24px;
  padding-right: 24px;
}
.sc-ion-searchbar-md-h{
  padding: 0px;
}
</style>
