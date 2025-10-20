<template>
<div id="submit">
    <frame-component>
        <slot></slot>
        <line-component></line-component>
        <img class="submit__img" src="../img/submit/submit.svg">
        <h3 class="submit__title">Submit your quote request</h3>
        <h4 class="submit__title__small">Please review all the information you previously typed in the past steps, and if all is okay, submit your message to receive a project quote in 24 - 48 hours.</h4>
        <btn-component @click="submit" label='Submit' color="button__blue" size="button-size__144px" font="button-font__main"></btn-component>
    </frame-component>
    <btn-component @click="toggle3" label='Previous step' color="button__white" size="button-size__193px" font="button-font__previous"></btn-component>
   
    

</div>


  
</template>


<script>
import BtnComponent from './BtnComponent.vue';
import FrameComponent from './FrameComponent.vue';
import LineComponent from './LineComponent.vue';

    export default {
        components: {                
                BtnComponent,
                FrameComponent,
                LineComponent
                
            },
            methods: {
                toggle3() {
                    this.$emit('toggle2', '3');
                },
                submit(e) {
                    this.$emit('submit', e);
                }
            },
        props: {
            elems: {
                type: Array,
                required: true
            }
        },
    }


</script>



<style scoped>
.submit__title {
    font-weight: 700;
    font-size: 24px;
    line-height: 146%;
    text-align: center;
    color: #170F49;
    margin: 18.3px;
}
.submit__title__small {
    font-weight: 400;
    font-size: 18px;
    line-height: 167%;
    text-align: center;
    color: #6F6C90;
    width: 495px;
    height: 106px;
    margin: 7.5px auto 12px;
}
.submit__img {
    display: block;
    width: 158px; 
    height: 145px;
    margin: 40px auto 18px;
}
.frame button {
    display: block;
    margin: 0px auto;
}

@media(max-width: 1199px) {
.submit__img {
    width: 105px;
    height: 120px;
    margin: 12px auto 8px;
}
.submit__title {
    margin: 15.3px;
}
.submit__title__small {
    font-size: 17px;
}
}


@media(max-width: 987px) {
.submit__title__small {
    width: 395px;
}
}

@media(max-width: 767px) {
.submit__title__small {
    font-size: 16px;
}
}
@media(max-width: 575px) {
.submit__title__small {
    width: 360px;
}
.submit__img {
    width: 105px;
    height: 90px;
}
}
@media(max-width: 459px) {
.submit__title__small{
    width: 330px;
}
.submit__title {
    margin: 12px;
}
.submit__img {
    height: 90px;
    margin: 10px auto 8px;
}
.submit__title__small {
    font-size: 16px;
}

}
</style>
