<template>
  <div id="checkbox">
    <form @submit.prevent>
        <frame-component>
            <slot></slot>
            <line-component></line-component>

             <h3 class="checkbox__title">Our services</h3>
            <h4 class="checkbox__title__small">Please select which service you are interested in.</h4>
            <div class="checkbox-wrap__small">
               <checkbox-comp :checkboxes="checkboxes" ></checkbox-comp>
               
            </div>
        
        <div class='error error__service' v-if="error" >{{ error }}</div>
        </frame-component>
            
        <div class="checkbox-button">
            
            <btn-component @click="toggle3" label='Previous step' color="button__white" size="button-size__193px" font="button-font__previous"></btn-component>
            
            <btn-component @click="toggle2"></btn-component>
            
            
        </div>
        
    </form>
  
  
  </div>

  
</template>


<script>
import BtnComponent from './BtnComponent.vue';
import CheckboxComp from './UI/CheckboxComp.vue';
import FrameComponent from './FrameComponent.vue';
import LineComponent from './LineComponent.vue';

    export default {
        components: {
            BtnComponent,
            CheckboxComp,
            FrameComponent,
            LineComponent

        },
        props: {
            elems: {
                type: Array,
                required: true
            },
            checkboxes: {
                type: Array,
                required: true
            }
        },
        data() {
            return {           
                selectedUsers: [
                    
                ],
                selUsers: [
                    
                ],
                obj: {

                },
                error: ''
            }
        },
        methods: {
        saveInput() {
           for (const checkbox of this.checkboxes) {

                    if (checkbox.checked) {
                    this.obj[checkbox.id] = checkbox.text;
                 
                } else {
                    this.error = 'Сервисы не выбраны';
                }
                     
                              
           }
            this.$emit('save', this.obj);  
            for (const checkbox of this.checkboxes) {
                if (checkbox.checked) {
                    checkbox.checked = false;
                }
            }
                      
            },  
                      
                           
           toggle2() {    
                this.validation();

                if (!this.error) {
                    this.saveInput();
                    this.$emit('toggle2', '3');

                }  else {   
                console.log('ничего не отмечено');
                }
            },
            toggle3() {
                this.$emit('toggle2', '1');
            },
            
            validation() {
               if (this.checkboxes.some(checkbox => {
                    return checkbox.checked})) {
               
                    this.error = null;
               } else {
                    this.error = 'Сервисы не выбраны';

               }
            }

        },    
        
    }


</script>



<style scoped>

.checkbox-elem__new {
    border: 1px solid #D9DBE9;
    border-radius: 16px;
    width: 284px;
    height: 114px;
    position: absolute;
    top: 0px;
    left: 0px;
}

.checkbox-wrap__small {
    width: 596px;
    height: 250px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;   
    margin-top: 39px; 
}
.checkbox__title {
    font-family: var(--font-family);
    font-weight: 700;
    font-size: 24px;
    line-height: 146%;
    color: #170F49;
    margin-top: 54px;

}
.checkbox__title__small {
    font-family: var(--font-family);
    font-weight: 400;
    font-size: 18px;
    line-height: 167%;
    color: #6F6C90;
}
.checkbox-button {
    display: flex;
    justify-content: space-between;
}
@media(max-width: 1199px) {
.checkbox-wrap__small {
    width: 506px;
}
.checkbox-button {
    width: 598px;
}
#checkbox {
    width: 598px;
}
.checkbox__title {   
    margin-top: 44px;
}
.checkbox-wrap__small {
    margin-top: 35px;
}
.error__service {
    bottom: 10px;
}
}
@media(max-width: 987px) {
    .checkbox-wrap__small {
        width: 406px;
        height: 220px;
    }    
    #checkbox {
        width: 498px;
    }
    .checkbox-button {
        width: 498px;
    }
    .error__service {
        bottom: 20px;
    }
}

@media(max-width: 767px) {
.checkbox-wrap__small {
    width: 390px;
}
#checkbox {
    width: 458px;
}
.checkbox-button {
    width: 458px;
}

.checkbox__title__small {
    font-size: 16px;
}
}
@media(max-width: 575px) {
#checkbox {
    width: 418px;
}
.checkbox-button {
    width: 418px;
}
.checkbox-wrap__small {
    width: 360px;
}
}
@media(max-width: 459px) {
#checkbox {
    width: 370px;
}

.checkbox-button {
    width: 370px;
}
.checkbox__title__small {
    font-size: 14px;
}
.checkbox-wrap__small {
    width: 340px;
}
}
</style>
