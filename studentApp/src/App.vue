<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet
  }
});
</script>
<style>
:root {
  --ion-color-primary: #358B84;
  --ion-color-primary-rgb: 53,139,132;
  --ion-color-primary-contrast: #ffffff;
  --ion-color-primary-contrast-rgb: 255,255,255;
  --ion-color-primary-shade: #2f7a74;
  --ion-color-primary-tint: #499790;
}
.ion-color-primary {  
  --ion-color-base: var(--ion-color-primary);  
  --ion-color-base-rgb: var(--ion-color-primary-rgb);  
  --ion-color-contrast: var(--ion-color-primary-contrast);  
  --ion-color-contrast-rgb: var(--ion-color-primary-contrast-rgb);  
  --ion-color-shade: var(--ion-color-primary-shade);  
  --ion-color-tint: var(--ion-color-primary-tint);  
}  
</style>