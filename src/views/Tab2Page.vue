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
        <div>
          <ion-searchbar placeholder="Custom Placeholder"></ion-searchbar>
        </div>
      </ExploreContainer>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonSearchbar, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';
import HeaderArea from "../components/HeaderArea.vue";
</script>
