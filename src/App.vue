<template>
<div>
    
    
    <header-component></header-component>
    
  </div>

  <div class="text__wrap">
  <h1>Get a project quote</h1>
  <h4 class="text__descr">Please fill the form below to receive a quote for your project. Feel <br> free to add as much detail as needed.</h4>
  </div>
  
  <div class="form__frame">
  
    <step-1 v-if="number==1" @toggle2="toggle2" @save="saveInformation" :elems="progress1">
        <progress-component :elems=" progress1"></progress-component>
    </step-1>
    <step-2 v-if="number==2" @toggle2="toggle2" :checkboxes="checkboxes" @save="saveInformation" :elems="progress2" >
      <progress-component  :elems=" progress2"></progress-component>
    </step-2>
    <step-3 v-if="number==3" @toggle2="toggle2"  @save="saveInformation" :elems="progress3">
      <progress-component  :elems=" progress3"></progress-component>
    </step-3>
    <step-4 v-if="number==4" @toggle2="toggle2" @submit="sendUser" :elems="progress4">
      <progress-component  :elems=" progress4"></progress-component>
    </step-4>
  </div>
  <footer-component class="footer"></footer-component>
  
</template>


<script>
import FooterComponent from './components/FooterComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import Step1 from './components/Step1.vue';
import Step2 from './components/Step2.vue';
import Step3 from './components/Step3.vue';
import ProgressComponent from './components/ProgressComponent.vue';
import Step4 from './components/Step4.vue';

export default {
  components: {
  
   Step2,
   Step1,
   Step3,
   ProgressComponent,
   Step4,
   HeaderComponent,
   FooterComponent
  },
  data() {
    return {
    checkboxes: [
        {id: 1, text:'development', label: 'Development', checked: false, src: "/img/checkbox/development.svg"},
        {id: 2, text:'design', label: 'Web Design', checked: false, src: "/img/checkbox/design.svg"},
        {id: 3, text:'marketing', label: 'Marketing', checked: false, src: "/img/checkbox/marketing.svg"},
        {id: 4, text:'other', label: 'Other', checked: false, src: "/img/checkbox/other.svg"}
      ],
      progress1: [
        {id: 1,  number: "1", color: "#4A3AFF", numberColor: "white", lineColor: "#EFF0F7", display: "block", shotLine: "block"},
        {id: 2,  number: "2", color: "#EFF0F7", numberColor: "#6F6C90", lineColor: "#EFF0F7", display: "block", shotLine: "none"},
        {id: 3,  number: "3", color: "#EFF0F7", numberColor: "#6F6C90", lineColor: "#EFF0F7", display: "block", shotLine: "none"},
        {id: 4,  number: "4", color: "#EFF0F7", numberColor: "#6F6C90", lineColor: "#EFF0F7", display: "none", shotLine: "none"}
      ],
      progress2: [
        {id: 1,  number: "1", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "block", shotLine: "none"},
        {id: 2,  number: "2", color: "#4A3AFF", numberColor: "white", lineColor: "#EFF0F7", display: "block", shotLine: "block"},      
        {id: 3,  number: "3", color: "#EFF0F7", numberColor: "#6F6C90", lineColor: "#EFF0F7", display: "block", shotLine: "none"},
        {id: 4,  number: "4", color: "#EFF0F7", numberColor: "#6F6C90", lineColor: "#EFF0F7", display: "none", shotLine: "none"}
      ],
      progress3: [
        {id: 1,  number: "1", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "block", shotLine: "none"},
        {id: 2,  number: "2", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "block", shotLine: "none"},      
        {id: 3,  number: "3", color: "#4A3AFF", numberColor: "white", lineColor: "#EFF0F7", display: "block", shotLine: "block"},
        {id: 4,  number: "4", color: "#EFF0F7", numberColor: "#6F6C90", lineColor: "#EFF0F7", display: "none", shotLine: "none"}
      ],
      progress4: [
        {id: 1,  number: "1", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "block", shotLine: "none"},
        {id: 2,  number: "2", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "block", shotLine: "none"},      
        {id: 3,  number: "3", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "block", shotLine: "none"},
        {id: 4,  number: "4", color: "#4A3AFF", numberColor: "white", lineColor: "#4A3AFF", display: "none", shotLine: "none"}
      ],
      newUser: [
      
      ],
      lastUser: {
      
      },
      number: 1,
    
    }
  },
  methods: {
    saveInformation(information) {
     this.newUser.push(information);
     Object.assign(this.lastUser, information);
     
      console.log(information);
      console.log(this.newUser);
      console.log(this.lastUser);
      
          
    },
    toggle2(component) {
      console.log(component);
      this.number = component;
    },
    sendUser() {
    for (const key in this.lastUser) {
      localStorage.setItem(key, this.lastUser[key])
}
      
  
      
    }
    
   
  }
  
 
}




</script>



<style>
app {
  
}
#app {
  display: block;
  max-width: 1440px;
  min-height: 100vh;  
  overflow: hidden;  
  transform: scale(1); 
  transform-origin: 0 0; 
 
}
.active {
  display: block;
}
.active__no {
  display: none;
}
#button {
  width: 204px;
  height: 214px;
  border: 3px solid green;
}
#button__previous {
  width: 204px;
  height: 214px;
  border: 3px solid red;
}
.progress-bar {
  width: 539px;
  height: 34px;
  display: flex;
  justify-content: space-between;
  margin-top: 12.47px;
  margin-bottom: 32.43px;
}
h1 {
  font-weight: 700;
  font-size: 34px;
  text-align: center;
  color: #170F49;
}
.text__descr {
  font-weight: 400;
  font-size: 18px;
  text-align: center;
  color: #6F6C90;
  text-align: center;
  margin-top: 12px;
}
.text__wrap {
  width: 699px;
  height: 171px;
  text-align: center;
  margin: 12px auto 0px;
}
.form__frame {
  height: 698.6px;
  width: 698px;
  margin: 0px auto;
}
.footer {
  margin-top: 100px;
}
@media(max-width: 1460px) {
#app {
  width: 1190px;
}

}
@media(max-width: 1199px) {
.form__frame {
  width: 598px
}
}
@media(max-width: 987px) {
.form__frame {
  width: 498px;
}
.text__wrap {
    width: 499px;
}
#app {
  height: 1243px;
}
}

@media(max-width: 767px) {
h1 {
  font-size: 30px;
}
.form__frame {
  height: 600px;
}
#app {
  height: 1143px;
}
.form__frame {
  width: 458px;
}
.text__wrap {
  width: 459px;
}
.text__descr {
  font-size: 16px;
}
}
@media(max-width: 575px) {
    .form__frame {
        width: 418px;
    }
    .text__wrap {
      width: 418px;
    }
    #app {
      width: 450px;
    }
}
@media(max-width: 459px) {
.form__frame {
  width: 380px;
}
.text__wrap {
    width: 370px;
}
}
</style>
