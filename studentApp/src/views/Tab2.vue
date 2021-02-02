<template>
  <ion-page>
    <ion-content>
      <ion-header>
        <ion-toolbar>
          <ion-title>Viata de Student</ion-title>
        </ion-toolbar>
      </ion-header>
    <div class="flex w-full flex-col overflow-auto">
      <div class="flex w-full flex-row flex-wrap justify-around mt-2">
        <ion-card class="w-2/5">
          <router-link :to="{name:'Courses'}">
            <ion-card-header>
              <ion-icon :icon="libraryOutline" color="primary" size="large"></ion-icon>
            </ion-card-header>
            <ion-card-content>
              <ion-card-title class="text-2xl">Courses</ion-card-title>
              <ion-card-subtitle>Tasks</ion-card-subtitle>
            </ion-card-content>
          </router-link>
        </ion-card>
        <ion-card class="w-2/5">
          <router-link :to="{name:'Seminars'}">
            <ion-card-header>
              <ion-icon :icon="easelOutline" color="primary" size="large"></ion-icon>
            </ion-card-header>
            <ion-card-content>
              <ion-card-title class="text-2xl">Seminars</ion-card-title>
              <ion-card-subtitle>Tasks</ion-card-subtitle>
            </ion-card-content>
          </router-link>
        </ion-card>
        <ion-card class="w-2/5">
          <router-link :to="{name:'Projects'}">
            <ion-card-header>
              <ion-icon :icon="constructOutline" color="primary" size="large"></ion-icon>
            </ion-card-header>
            <ion-card-content>
              <ion-card-title class="text-2xl">Project</ion-card-title>
              <ion-card-subtitle>Tasks</ion-card-subtitle>
            </ion-card-content>
          </router-link>
        </ion-card>
        <ion-card class="w-2/5">
          <router-link :to="{name:'Exams'}">
            <ion-card-header>
              <ion-icon :icon="documentsOutline" color="primary" size="large"></ion-icon>
            </ion-card-header>
            <ion-card-content>
              <ion-card-title class="text-2xl">Exams</ion-card-title>
              <ion-card-subtitle>Tasks</ion-card-subtitle>
            </ion-card-content>
          </router-link>
        </ion-card>
      </div>
    </div>
    </ion-content>
    <div>
      <ion-fab @click="isOpenNewTask = true" vertical="bottom" horizontal="end" slot="fixed">
        <ion-fab-button>
            <ion-icon :icon="addOutline"></ion-icon>
        </ion-fab-button>
      </ion-fab>
      <ion-modal :is-open="isOpenNewTask" :backdrop-dismiss="false">
          <new-event @closeModal="isOpenNewTask = false"></new-event>   
      </ion-modal>
    </div>
  </ion-page>
</template>

<script lang="ts">
import {ref} from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonCard,IonCardHeader,IonIcon,IonCardContent,IonCardTitle,
IonCardSubtitle, IonFab, IonFabButton, IonModal} from '@ionic/vue';
import {documentsOutline, libraryOutline, constructOutline, easelOutline, addOutline} from 'ionicons/icons'; 
import NewEvent from '../components/NewEvent.vue'

export default  {
  name: 'Tab2',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage,
                IonCard,IonCardHeader,IonIcon,IonCardContent,IonCardTitle,
                IonCardSubtitle, IonFab, IonFabButton, IonModal, 
                NewEvent
              },
  setup(){
    const isOpenNewTask = ref(false);
    return {
      documentsOutline, libraryOutline, constructOutline, easelOutline, addOutline,
      isOpenNewTask
    }
  }
} 

</script>