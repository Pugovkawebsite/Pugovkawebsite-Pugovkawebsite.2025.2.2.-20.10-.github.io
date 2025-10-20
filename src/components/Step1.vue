<template>
  <div id="input-main__content">
  <form action="#" @submit.prevent>
    <div class="form-main">

    <div class="input-main__wrap__big">

    
    <slot></slot>
        <line-component></line-component>
    <h3 class="input-main__title">Contact details</h3>
    <h4 class="input-main__title__small">Lorem ipsum dolor sit amet consectetur adipisc.</h4>
      <div class="input-main__wrap__small">  
        
        <input-main-comp label="Name" name="name" placeholder='Name' :value='input.name' @change="input.name=$event.target.value" @blur="validateName" src="../img/Name.svg"></input-main-comp>
        <span v-if="errors.name" class="error error__name">{{ errors.name }}</span>
        <input-main-comp label="Email" name="email"  :value='input.email' @change="input.email=$event.target.value" src="../img/Email.svg" @blur="validateEmail"></input-main-comp>
        <span v-if="errors.email" class="error error__email">{{ errors.email }}</span>
        <input-main-comp label="Phone Number" name="number" :value='input.number' @change="input.number=$event.target.value" src="../img/Phone.svg" @blur="validateNumber"></input-main-comp>
        <span v-if="errors.number" class="error error__number">{{ errors.number }}</span>
        <input-main-comp label="Company" name="company" :value='input.company' @change="input.company=$event.target.value" src="../img/Company.svg" @blur="validateCompany"></input-main-comp>
        <span v-if="errors.company" class="error error__company">{{ errors.company }}</span>
        </div>
    </div>
    </div>
    <btn-component @click="toggle2"></btn-component>
    
    
  </form>
  
  
  </div>

  
</template>


<script>

import InputMainComp from './UI/InputMainComp.vue';
import BtnComponent from './BtnComponent.vue';
import LineComponent from './LineComponent.vue';

    export default {
        components: {
            InputMainComp,
            BtnComponent,
            LineComponent
        },
        data() {
            return {
                input: {
                    name: "",
                    email: "",
                    number: "",
                    company: ""
                },
                errors: {
                    name: '',
                    email: '',
                    number: " ",
                    company: " "
                }
            }
        },
       
        
        
        methods: {
            saveInput() {
                this.input.id = Date.now();
                this.$emit('save', this.input);
                console.log(this.input);
                
                
            },           
            toggle2() {
            this.validateName();
            this.validateEmail();
            this.validateNumber();
            this.validateCompany();
            if (!this.errors.name) {
                this.$emit('toggle2', '2');
                this.saveInput();
                }
                
            },
            validateName() {      
                if (this.input.name) {
                    this.errors.name = '';                    
                } else {
                    this.errors.name = 'Имя обязательно';                
                }
            },
            validateEmail() {
                
                const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                if (!this.input.email) {
                    this.errors.email = 'Email обязателен';
                } else if (!emailPattern.test(this.input.email)) {
                    this.errors.email = 'Введите корректный Email';
                } else {
                    this.errors.email = '';
                }
            },
            validateNumber() {
                const numberPattern = /\d+/;
                if (!this.input.number) {
                    this.errors.number = 'Телефон обязателен';
                } else if (!numberPattern.test(this.input.number)) {
                    this.errors.number = 'Введите корректный номер';
                } else {
                    this.errors.number = '';
                }   
                
            },
            validateCompany() {
      
                if (this.input.company) {
                    this.errors.company = '';
                    
                } else {
                    this.errors.company = 'Компания не указана';
                
                }
            },
        }
    }


</script>



<style scoped>
.form-main {
    border: 1px solid #D9DBE9;
    border-radius: 34px;
    width: 698px;
    height: 606px;
    box-shadow: 0 5px 16px 0 rgba(8, 15, 52, 0.06);
    background: white;
    padding: 32px 50px 80px 50px;
    margin-bottom: 31.61px;
}
.error {
    position: absolute;
    color: red;
    bottom: 0px;
}
.error__email {
    right: 0px;
}
.error__number {
    bottom: -20px;
}
.error__company {
    right: 0px;
    bottom: -20px;
}
.input-main__wrap__big {
    width: 596px;
    height: 362px;
}
.input-main__title {
    font-weight: 700;
    font-size: 34px;
    color: #170F49;
    margin-bottom: 7.5px;
    margin-top: 64px;
}
.input-main__title__small {
    font-weight: 400;
    font-size: 18px;
    color: #6F6C90;
    margin-bottom: 39px;
}
.input-main__wrap__small {
    width: 596px;
    height: 250px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    position: relative;
}
form {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: end;
}



@media(max-width: 1199px) {
.form-main {
    width: 598px;
    height: 506px;
}
.input-main__wrap__small {
    width: 496px;
    height: 190px;
}
.input-main__wrap__big {
    width: 496px;
}
.line {
    width: 496px;
}
.input-main__title {
    margin-top: 44px;
}
.error__number {
    bottom: -35px;
}
.error__company {
    bottom: -35px;
}
.error__email {    
    bottom: -11px;
}
.error__name {
    bottom: -11px;
}
}
@media(max-width: 987px) {
    .form-main {
        width: 498px;
    }    
    .input-main__wrap__small {
        width: 406px;
    }
    .input-main__wrap__big {
        width: 396px;
    }
    .line {
        width: 396px;
    }
    
    
     
}
@media(max-width: 767px) {
.form-main {
    width: 458px;
    padding: 32px 35px 60px 35px;
}
.input-main__wrap__small {
    width: 386px;
}
.input-main__title {
    font-size: 30px;
}
.button-blue__next {
    padding: 20px 20px 21px;
    width: 145px;
    font-size: 16px;
}
.input-main__title__small {
    font-size: 16px;
}
}
@media(max-width: 575px) {
.form-main {
    width: 418px;
    padding: 32px 30px 50px 30px;
}
.line{
    width: 356px;
}
.input-main__title {
    font-size: 24px;
}
.input-main__wrap__big {
    width: 356px;
}

.input-main__wrap__small {
    width: 356px;
}
.button-blue__next {
    width: 135px;
}
}
@media(max-width: 459px) {

.form-main {
  width: 370px;
  padding: 32px 20px 50px 20px;
}
.line {
    width: 330px;
}
.input-main__wrap__small {
    width: 335px;
}
.input-main__title {
    font-size: 26px;
}
.button-blue__next {
    padding: 10px 10px 11px;
}
.input-main__title__small {
    font-size: 14px;
}

}
</style>
