<template>
    <div v-for="radio in radios" :key="radio.id" class="radio__frame">
         <input :id="radio.id"  class="radio-elem" type="radio" name="budget" :value="radio.value" v-model="radio.budget">
        <label :for="radio.id">{{radio.value}}</label>
    </div>
    
  
</template>


<script>
    export default {
        
        props: {
            radios: {
                type: Array,
                required: true
            }
        }
    }


</script>



<style scoped>
.radio__frame label {
    display: inline-block;
    border: 1px solid #D9DBE9;
    border-radius: 16px;
    width: 284px;
    height: 114px;
    box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
    background: white;
    padding-left: 70px;
    padding-top: 48px;
}

.radio__frame input {
    position: absolute;
    left: 35px;
    top: 51px;
    border-radius: 100%;
    fill: #D9DBE9;
    stroke-width: 1.20px;
    stroke: #D9DBE9;
    box-shadow: inset 0 -3px 7px 0 rgba(20, 20, 43, 0.08);
   
}
.radio__frame input:checked+ label {
    box-shadow: 0 4px 10px 0 rgba(31, 37, 89, 0.07), 0 2px 11px 0 rgba(69, 65, 164, 0.06);
    background: white;
    fill: #4A3AFF; 
    border: 2px solid #4A3AFF;

}
.radio__frame input:checked {
    display: none;
}
.radio__frame input + label::before {
    content: '';
    position: absolute;
    left: 35px;
    top: 40px;
    background-image: url("src/img/radio/radio.svg");
    display: none;
    
}
.radio__frame input:checked + label::before {
    display: block;
    z-index: 1000;
    width: 25px;
    height: 25px;
}
.radio__frame {
    position: relative;
}

@media(max-width: 1199px) {
.radio__frame label {
    width: 244px;
    height: 104px;
    padding-top: 42px;
}
.radio__frame input {
    top: 44px;
}
}
@media(max-width: 987px) {
.radio__frame label {
    width: 194px;
    height: 94px;
    padding-top: 39px;
    padding-left: 60px;
}
.radio__frame input {
    left: 27px; 
}
.radio__frame label {
    padding-left: 50px;  
}
.radio__frame input + label:before {
    left: 25px;
    top: 36px;
}
.progress__ball {
    width: 31px;
    height: 31px;
}
}
@media(max-width: 767px) {
.radio__frame label {
    width: 184px;
    height: 90px;
    padding-top: 35px;
    padding-left: 46px;
}
.radio__frame input {
    top: 38px;
}
.radio__frame input{
    left: 30px;
}
.radio__title__small {
    font-size: 15px;
}
.radio__frame input + label:before {
    left: 21px;
    top: 32px;
}
}
@media(max-width: 575px) {
.radio__frame label {
    font-size: 14px;
    width: 164px;
    height: 90px;
    padding-top: 35px;
    padding-left: 35px;
}
.radio__frame input {
    left: 16px;
}
.radio__frame input + label:before {
        left: 8px;
}
}
@media(max-width: 459px) {
.radio__frame label {
    width: 154px;
    height: 80px;
    padding-top: 30px;
    padding-left: 30px;
}
.radio__frame input {
    left: 10px;
    top: 33px;
}
.radio__frame input:checked + label:before {
    left: 2px;
    top: 26px;
}
}
</style>
