<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Sex Predictor</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Sex Predictor</ion-title>
        </ion-toolbar>
      </ion-header>

      <SexPredictor />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import SexPredictor from '@/components/SexPredictor.vue';
</script>
