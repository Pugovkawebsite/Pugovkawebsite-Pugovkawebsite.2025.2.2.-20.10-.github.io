<template>
    <div class="checkbox-elem" :key="checkbox.id" v-for="checkbox in checkboxes">
        <input type="checkbox" class="checkbox"  :id="checkbox.id" :value="checkbox.text"  :checked="checkbox.checked" v-model="checkbox.checked">
        <label class="checkbox-elem__label" :for="checkbox.id">{{checkbox.label}}</label>
        <img class="checkbox-elem__img" :src="checkbox.src">
    </div>

  
</template>


<script>
    export default {
        
        props: {            
            checkboxes: {
                type: Array,
                required: true
            },
            
        },
        
    }


</script>



<style scoped>
.checkbox:checked {
    border: 2px solid #4A3AFF;
    box-shadow: 0 4px 10px 0 rgba(31, 37, 89, 0.07), 0 2px 11px 0 rgba(69, 65, 164, 0.06);
}
.checkbox-elem {
    width: 284px;
    height: 114px;
    position: relative;
}
.checkbox {
    appearance: none;
    position: relative;
    border: 1px solid #D9DBE9;
    border-radius: 16px;
    width: 284px;
    height: 114px;
    position: relative;
}
.checkbox-elem__label {
    font-weight: 500;
    font-size: 18px;
    color: #170F49;
    position: absolute;
    top: 47px;
    left: 105px;
}
.checkbox-elem__img {
    position: absolute;
    top: 24px;
    left: 26px;
}
@media(max-width: 1199px) {
.checkbox-elem {
    width: 224px;
}
.checkbox {
    width: 224px;
    height: 100px;
}
.checkbox-elem__img {
    top: 18px;
    width: 25%;
}
}
@media(max-width: 987px) {
    .checkbox-elem {
        width: 190px;
        height: 90px;
    }
    .checkbox {
        width: 190px;
        height: 90px;
    }
    .checkbox-elem__label {
        font-size: 16px;
        top: 40px;
        left: 85px;
    }
    .checkbox-elem__img {
        width: 25%;
        left: 16px;
        top: 15px;
    }
}
@media(max-width: 767px) {
.checkbox-elem__label {
    font-size: 15px;
    top: 34px;
}
}
@media(max-width: 575px) {
.checkbox-elem {
    width: 170px;
    height: 80px;
}
.checkbox {
    width: 170px;
    height: 80px;
}
.checkbox-elem__label {
    top: 30px;
    left: 70px;
}
}
@media(max-width: 459px) {
.checkbox {
    width: 155px;
}
.checkbox-elem__label {
    left: 58px;
}
.checkbox-elem__img {
    left: 11px;
    top: 16px;
}
}
</style>
