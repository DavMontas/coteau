<template>
  <ion-page>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <img src="https://cdn-icons-png.flaticon.com/512/479/479404.png" alt="" />

        </ion-toolbar>
      </ion-header>

      <Presentation />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import Presentation from '@/components/Presentation-comp.vue'

</script>

<style scoped>
  img{
    margin: 0 auto;
    height: 300px;
    width: 100%;

  }
</style>