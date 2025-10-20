<template>
    <div class="input-main"> 
            <label class="input-main__label" :for=name>{{label}}</label>
            <input class="input-real" :name=name :placeholder=placeholder type='text' :value=value >
            <img class="input-main__img" :src=src>
            
    </div>
    
  






</template>


<script>

export default {
        props: {
            label: {
                type: String,
            },
            name: {
                type: String,
            },
            placeholder: {
                type: String,
            },
            value: {
                type: Object,
            },
            src: {
                type: String,
            },
            
        }
    }


</script>



<style scoped>
.input-main {
    width: 284px;
    height: 105px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
}
.input-main__label {
    font-weight: 500;
    font-size: 18px;
    color: #170F49;
}
.input-real {
    border: 1px solid #D9DBE9;
    border-radius: 46px;
    width: 284px;
    height: 66px;
    box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
    background: white;
    padding-left: 20.72px;
    
    
}
.input-real::placeholder {
    font-weight: 400;
    font-size: 18px;
}
.input-main__img {
    position: absolute;
    width: 23px;
    height: 29px;
    bottom: 20.09px;
    right: 22.25px;
}


@media(max-width: 1199px) {
.input-main {
    width: 234px;
    height: 85px;
}
.input-real {
    width: 234px;
    height: 56px;
}
}
@media(max-width: 987px) {
    .input-main {
        width: 194px;
        height: 75px;
    }
    .input-main__label {
        font-size: 16px;
    }
    .input-real {
        width: 194px;
        height: 50px;
    }
    .input-main__img {
        bottom: 10.09px;
    }
}
@media(max-width: 767px) {
.input-main {
    width: 174px;
}
.input-real {
    width: 174px;
}
.input-main__label {
    font-size: 15px;
}
}
@media(max-width: 575px) {

}
@media(max-width: 459px) {
.input-main {
    width: 164px;
}
.input-real {
    width: 164px;
}
.input-main__img {
    height: 23px;
    right: 12.25px;
}
}
</style>
