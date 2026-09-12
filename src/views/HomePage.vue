<template>
  <ion-page>
      <ion-header>
        <ion-toolbar> <ion-title> My Photo Gallery </ion-title> </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <camera @photo-captured="addPhoto" />
        <photo :photos="photos" />
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
} from "@ionic/vue";
import { ref } from "vue";
import camera from "@/components/camera.vue";
import photo from "@/components/photo.vue";
const photos = ref<string[]>([]);
const addPhoto = (photo: string) => {
  photos.value.unshift(photo);
};
</script>