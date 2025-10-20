<template>
<div class="header__wrap">
    <img class="header__img" src="../img/header/header.svg">
    <btn-component label='Clone now' size="button-size__171px" font="button-font__main"></btn-component>
</div>

  
</template>


<script>
import BtnComponent from './BtnComponent.vue';

    export default {
    components: {
            BtnComponent

        },
        
    }


</script>



<style scoped>
.header__btn {
    width: 171px;
}
.header__wrap {
    width: 100%;
    height: 126px;
    padding: 0px 99px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
@media(max-width: 987px) {
.header__img {
    width: 45%;
}
.header__btn {
    width: 161px;
    padding: 10px 30px 11px;
}
}
@media(max-width: 767px) {
.header__btn {
    width: 141px;
    padding: 10px 10px 11px;
    font-size: 16px;
}
.header__wrap {
    padding: 0px 49px;
}
}
@media(max-width: 459px) {
.button-blue__next {
    height: 51px;
    width: 131px;
}
}
</style>
