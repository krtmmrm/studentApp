<template>
  <ion-page>
    <ion-tabs>
      <ion-tab-bar slot="bottom">
        <ion-tab-button tab="settings" href="/tabs/tab1">
           <ion-icon :icon="settingsOutline"/>
          <ion-label>Settings</ion-label>
        </ion-tab-button>
          
        <ion-tab-button tab="home" href="/tabs/tab2">
          <ion-icon :icon="homeOutline"/>
          <ion-label>Home</ion-label>
        </ion-tab-button>
        
        <ion-tab-button tab="calendar" href="/tabs/tab3">
          <ion-icon :icon="calendarOutline"/>
          <ion-label>Calendar</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts">
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonIcon, IonPage } from '@ionic/vue';
import { settingsOutline, homeOutline, calendarOutline } from 'ionicons/icons';

export default {
  name: 'Tabs',
  components: { IonLabel, IonTabs, IonTabBar, IonTabButton, IonIcon, IonPage },
  setup() {
    return {
      settingsOutline, 
      homeOutline, 
      calendarOutline
    }
  }
}
</script>