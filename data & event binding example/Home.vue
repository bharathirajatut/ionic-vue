<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div id="container">
        <!--
        <h4>Variable Binding</h4>
        <p>Name: {{name}}</p> 

        <h4>Object Binding</h4>
        <p>Name: {{emp.name}} , Age: {{emp.age}}</p> 
        -->
        <ion-item>
    <ion-label position="stacked">Value1</ion-label>
    <ion-input v-model="value1"></ion-input>
  </ion-item>

  <ion-item>
    <ion-label position="stacked">Value2</ion-label>
    <ion-input v-model="value2"></ion-input>
  </ion-item>

    <ion-button v-on:click="add" expand="block">Add</ion-button>

    <p style="margin-top:10%"> 
      Total: {{total}}
    </p>

      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar,
IonButton,IonItem,IonInput,IonLabel } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonButton,
    IonItem,
    IonInput,
    IonLabel
  },
  data(){
     return{
      name:"Raja",
      emp:{name:'Ram',age:25},
      value1:'',
      value2:'',
      total:0
    }
  },
  methods:{

    add()
    {
      this.total=parseFloat(this.value1)+parseFloat(this.value2)
    }
  }
});
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 40%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}

</style>