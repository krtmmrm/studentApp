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
       <Form class="flex flex-col justify-center h-full">

           <div>
               <ion-item>
                 <ion-icon :icon="createOutline" color="primary" slot="start"></ion-icon>
                   <Field v-slot="{ field }" name="taskField" 
                   :rules="isRequired" v-model="task"> 
                       <ion-input v-bind="field" type="text" name="taskField"
                       placeholder="Add new event here..."></ion-input>
                   </Field>    
               </ion-item>
               <ion-item lines="none">
                   <ErrorMessage v-slot="{message}" name="taskField">
                       <ion-text color="danger" v-if="message">{{message}}</ion-text>
                   </ErrorMessage>
               </ion-item>
           </div>
            <div>
               <ion-item>
                   <ion-icon :icon="calendarOutline" color="primary" slot="start"></ion-icon>
                   <Field v-slot="{field}" name="duedateField" :rules="isRequired"> 
                       <ion-datetime v-bind="field" v-model="dueDate"
                       display-format="MMM DD, YYYY HH:mm"
                       display-timezone="utc"
                       value="2020-11-11T14:51:56.646+01:00" max="2025-12-31"></ion-datetime>
                   </Field>
               </ion-item>
               <ion-item lines="none">
                   <ErrorMessage v-slot="{message}" name="duedateField">
                       <ion-text color="danger" v-if="message">{{message}}</ion-text>
                   </ErrorMessage>
               </ion-item>

               <ion-item>
                   <ion-icon :icon="clipboardOutline" color="primary" slot="start"></ion-icon>
                   <ion-textarea v-model="note" placeholder="Enter more information here..."></ion-textarea>
               </ion-item>
                <ion-item lines="none"></ion-item>

               <ion-item>
                   <ion-icon :icon="folderOpenOutline" color="primary" slot="start"></ion-icon>
                   <ion-label>Category</ion-label>

                   <Field v-model="category" :rules="isRequired" v-slot="{field}" name="categoryField" >
                       <ion-select v-bind="field" placeholder="Select One">
                            <ion-select-option value="Course">Course</ion-select-option>
                            <ion-select-option value="Seminar">Seminar</ion-select-option>
                            <ion-select-option value="Project">Project</ion-select-option>
                            <ion-select-option value="Exam">Exam</ion-select-option>
                       </ion-select>
                   </Field>
               </ion-item>
               <ion-item lines="none">
                   <ErrorMessage v-slot="{message}" name="categoryField">
                       <ion-text color="danger" v-if="message">{{message}}</ion-text>
                   </ErrorMessage>
               </ion-item>

           </div>

           <div class="mt-8">
               <ion-button expand="block" type="submit">Create</ion-button>
           </div>
        </Form> 

  </ion-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import { IonPage,IonFab,IonIcon,IonItem,IonInput,IonText,IonDatetime,IonTextarea,
IonLabel, IonButton, IonSelect,IonSelectOption, IonHeader, IonToolbar, IonTitle } from '@ionic/vue';
import {close,calendarOutline, folderOpenOutline, clipboardOutline, createOutline} from 'ionicons/icons';
import { Form, Field, ErrorMessage } from 'vee-validate';
export default defineComponent ({
    components:{
        IonPage, IonHeader, IonToolbar, IonTitle,  IonFab, IonIcon,IonItem,IonInput,IonText,IonDatetime,IonTextarea,
        IonLabel, IonButton, IonSelect,IonSelectOption,
        Form, Field, ErrorMessage 
    },
    setup(){
        const task = ref('');
        const dueDate = ref('');
        const note = ref('');
        const category = ref('');
        const isRequired = (value) => {
            if (!value) {
                return 'This field is required';
            }
            return true;
        }
        return {
            close, isRequired, task, dueDate, note, category,
            folderOpenOutline, calendarOutline, clipboardOutline, createOutline
        }
    }
})
</script>

<style>

</style>