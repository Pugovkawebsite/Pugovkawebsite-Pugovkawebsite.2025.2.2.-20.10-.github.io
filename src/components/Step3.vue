<template>
  <div id="radio">
    <form name="myForm" @submit.prevent>
    <frame-component>
        <slot></slot>
        <line-component></line-component>
            <h3 class="radio__title">What’s your project budget?</h3>
            <h4 class="radio__title__small">Please select the project budget range you have in mind.</h4>
        <div class="radio__wrap">
            <radio-comp :radios="radios"></radio-comp>
        </div>
        <div class='error' v-if="error" >{{ error }}</div>
    </frame-component>
    <div class="radio-button">
        
        <btn-component @click="toggle3" label='Previous step' color="button__white" size="button-size__193px" font="button-font__previous"></btn-component>
        <btn-component @click="toggle2"></btn-component>
        
    </div>
      
        
    </form>
   
  
  
  </div>

  
</template>


<script>
import BtnComponent from './BtnComponent.vue';
import RadioComp from './UI/RadioComp.vue';
import FrameComponent from './FrameComponent.vue';
import LineComponent from './LineComponent.vue';




    export default {
        components: {
            BtnComponent,
            RadioComp,
            FrameComponent,
            LineComponent
        },
        data() {
            return {
                budget: {
                    budget: ''
                },
                error: '',
                radios: [
                    {id: 1, text: '5000', value: '$5.000 - $10.000', budget: ''},
                    {id: 2, text: '10000', value: '$10.000 - $20.000', budget: ''},
                    {id: 3, text: '20000', value: '$20.000 - $50.000', budget: ''},
                    {id: 4, text: '50000', value: '$50.000 +', budget: ''}
                ]
            }
        },
        props: {
            elems: {
                type: Array,
                required: true
            }
        },
        methods: {
           chooseRadio() {
           for (const radio of this.radios) {
                if (radio.budget) {
               
                this.budget.budget = radio.budget;
                
                console.log(this.budget);
                this.$emit('save', this.budget);
                }
           }

                      
            },
            toggle2() {
                this.validation();
                if (!this.error) {
                    this.chooseRadio();
                    this.$emit('toggle2', '4');
                } else {
                    console.log('Бюджет не выбран');
                }

                
            },
            toggle3() {
                this.$emit('toggle2', '2');
            },
            
            validation() {
                if (this.radios.some(radio => {
                    return radio.budget})) {
               
                    this.error = null;
               } else {
                    this.error = 'Бюджет не выбран';

               }
            }
            
           
           
        },    
        
    }


</script>



<style scoped>

.form_toggle {
	display: inline-block;
	overflow: hidden;
}
.form_toggle-item {
	float: left;
	display: inline-block;
}
.form_toggle-item input[type=radio] {
	display: none;
}
.form_toggle-item label {
	display: inline-block;
	padding: 0px 15px;   
	line-height: 34px;    
	border: 1px solid #999;
	border-right: none;
	cursor: pointer;
	user-select: none;   
}
 
.form_toggle .item-1 label {
	border-radius: 6px 0 0 6px;
}
.form_toggle .item-2 label {
	border-radius: 0 6px 6px 0;
	border-right: 1px solid #999;
}
 
/* Checked */
.form_toggle .item-1 input[type=radio]:checked + label {
	background: #ffc5c5;
}
.form_toggle .item-2 input[type=radio]:checked + label {
	background: #bbffbb;
}



.radio__wrap {
    width: 596.09px;
    height: 251px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap; 
    margin-top: 40px;
}
.radio__title {
    font-weight: 700;
    font-size: 24px;
    line-height: 146%;
    color: #170F49;
    margin-top: 64px;
}
.radio__title__small {
    font-weight: 400;
    font-size: 18px;
    line-height: 167%;
    color: #6F6C90;
    margin-top: 7.5px;
}
.radio-button {
    display: flex;
    justify-content: space-between;
}
@media(max-width: 1199px) {
.radio__wrap {
    width: 496.09px;
    height: 221px;
    margin-top: 30px;
}
.radio__title {
    margin-top: 44px;
}
}
@media(max-width: 987px) {
.radio__wrap {
    width: 396.09px;
    height: 201px;
     margin-top: 15px;
}
}
@media(max-width: 767px) {
.radio__title__small {
    font-size: 15px;
}
}
@media(max-width: 575px) {
.radio__wrap {
    width: 350.09px;
    height: 201px;
    margin-top: 15px;
}
}
@media(max-width: 459px) {
.radio__wrap {
    width: 330.09px;
}
}
</style>
