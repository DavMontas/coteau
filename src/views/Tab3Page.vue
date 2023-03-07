<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Age Predictor</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Age Predictor</ion-title>
        </ion-toolbar>
      </ion-header>

      <AgePredictor/>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import AgePredictor from '@/components/AgePredictor.vue';
</script>
