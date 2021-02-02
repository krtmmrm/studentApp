<template>
  <ion-page>
    <ion-header>
        <ion-toolbar>
          <ion-title>New Event</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-fab vertical="top" horizontal="end" slot="fixed"
        class="cursor-pointer" @click="$emit('close-modal')">
          <ion-icon :icon="close" class="text-3xl"></ion-icon>
      </ion-fab>
  </ion-page>
</template>

<script>
import { defineComponent } from "vue";
import { IonPage, IonHeader, IonToolbar, IonTitle, IonFab, IonIcon } from '@ionic/vue';
import { close } from 'ionicons/icons'

export default defineComponent ({
    components:{
        IonPage, IonHeader, IonToolbar, IonTitle,  IonFab, IonIcon
    },
    setup(){
        return {
            close
        }
    }
})
</script>

<style>

</style>