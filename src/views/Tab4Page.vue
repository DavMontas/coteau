<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>University Predictor</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">University Predictor</ion-title>
        </ion-toolbar>
      </ion-header>

      <UniversityComp />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import UniversityComp from '@/components/UniversityComp.vue';
</script>
