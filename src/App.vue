<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script setup lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
</script>
<style>
body{
  font-family: 'Inter', sans-serif;
}
.md.ion-page{
  max-width: 500px;
  margin: 0px auto;
  border: 1px solid #ddd;
}
</style>
