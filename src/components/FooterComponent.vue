<template>
 <div class="footer">
    <div class="footer__wrap">
        <div class="footer__label">
            <img class="footer__img" src="../img/header/header.svg">
            <div class="footer__text">Copyright © 2021 BRIX Templates | All Rights Reserved</div>
        </div>
        <div class="footer__input">
            <input placeholder="Enter your email">
            <btn-component label='Subscribe' size="button-size__129px" font="button-font__small"></btn-component>
        </div>
    </div>
 
 
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
.footer {
    width: 1440px;
    height: 195px;
    padding-right: 99px;
    padding-left: 99px;
    display: flex;
    align-items: center;
    border-top: 1px solid #D9DBE9;
}
.footer__wrap {
    height: 82px;
    width: 100%;
    display: flex;
    justify-content: space-between;
}
input {
    border: 1px solid #EFF0F7;
    border-radius: 60px;
    width: 507px;
    height: 73px;
    box-shadow: 0 8px 25px 0 rgba(13, 10, 44, 0.06);
    background: white;
    padding-left: 31px;
    padding-right: 147px;
    font-weight: 400;
    font-size: 18px;
    line-height: 111%;
    color: #6F6C90;
}
.footer__input {
    position: relative;
    width: 507px;
    height: 73px;
    
}
.footer button {    
    position: absolute;
    top: 12px;
    right: 17px;
   

}
.footer__label {
    width: 447px;
    height: 82px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
.footer__img {
    width: 262px;
    height: 35px;
}
.footer__text {
    font-weight: 400;
    font-size: 18px;
    line-height: 167%;
    color: #6F6C90;
}
@media(max-width: 1460px) {
.footer {
    width: 1190px;
}
}
@media(max-width: 1199px) {
.footer {
    width: 100%;
    padding-right: 50px;
    padding-left: 50px;
}
input {
    width: 407px;
}
.footer__input {
    width: 407px;
}
.footer__text {
    font-size: 16px;
}
}

@media(max-width: 987px) {
    input {
        width: 307px;
        font-size: 14px;
    }
    .footer__btn {
        width: 100px;
        font-size: 14px;
        padding: 14px 6px;
    }
    .footer {
        height: 155px;
    }
    .footer__input {
        width: 307px;
    }
        

}
@media(max-width: 767px) {
.footer__img {
    width: 202px;
}
.footer__text {
    font-size: 14px;
}
.footer {
    padding-right: 20px;
    padding-left: 20px;
}
input {
    width: 287px;
    padding-left: 18px;

}
.footer__input {
    width: 287px;
}
}
@media(max-width: 575px) {
    .footer__input {
        display: none;
    }
}
</style>
