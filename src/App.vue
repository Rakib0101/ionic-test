<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script setup lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
</script>
<style>
.md.ion-page{
  max-width: 500px;
  margin: 0px auto;
  border: 1px solid #ddd;
}
</style>
