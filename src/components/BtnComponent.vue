<template>
 <button :class='["button__next", color, size, font]'>{{label}}</button>

  
</template>


<script>
    export default {
        
        props: {
            label: {
                type: String,
                default: 'Next step'
            },
            color: {
                type: String,
                default: 'button__blue'
            },
            size: {
                type: String,
                default: 'button-size__165px'
            },
            font: {
                type: String,
                default: 'button-font__main'
            }
        }
    }


</script>



<style scoped>
.button__next {
    font-family: "DM Sans", sans-serif;
    border-radius: 56px;
    padding: 20px 40px 21px;
    text-align: center;
    cursor: pointer;
}
.button__blue {
    background: #4A3AFF;
    color: white;
    box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
    border: none;
}
.button__white {
    border: 1px solid #4A3AFF;
    color: #4A3AFF;
    background-color: white;
    border-radius: 66px;
}
.button__previous {
    border: 1px solid #4A3AFF;
    border-radius: 66px;
    padding: 19px 40px 21px;
    width: 193px;
    height: 60px;    
    font-weight: 400;
    font-size: 18px;
    text-align: center;
    color: #4A3AFF;
    background-color: white;
    cursor: pointer;
}
.button-size__165px {
    width: 165px;
    height: 61px; 
}
.button-size__193px {
    width: 193px;
    height: 60px; 
}
.button-size__171px {
    width: 171px;
    height: 61px; 
}
.button-size__129px {
    width: 129px;
    height: 49px; 
    padding: 15px 20px 21px;
}
.button-size__144px {
    width: 144px;
    height: 61px; 
}
.button-font__main {
    font-weight: 700;
    font-size: 18px;
}
.button-font__previous {
    font-weight: 400;
    font-size: 18px;
}
.button-font__small {
    font-weight: 500;
    font-size: 16px;
}

@media(max-width: 767px) {
.button-blue__next {
    padding: 20px 20px 21px;
    width: 145px;
    font-size: 16px;
}
.button__previous {
    padding: 19px 20px 21px;
    width: 143px;
    font-size: 16px;
}
}
@media(max-width: 575px) {
.button-size__193px {
    width: 180px;
    padding: 15px 30px 15px;
}
.button-size__171px {
    padding: 10px 30px 11px;
    width: 161px;
}
.button-blue__next {
    width: 135px;
}
.button__previous {
    padding: 19px 10px 21px;
    width: 135px;
}
}
@media(max-width: 459px) {
.button-size__193px {
    width: 160px;
    padding: 14px 20px 14px;
    font-size: 17px;
}
.button-blue__next {
    padding: 10px 20px 11px;
    height: 51px;
    font-size: 16px;
}
}
</style>
