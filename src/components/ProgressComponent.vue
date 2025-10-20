<template>


<div class="progress-bar"> 
  <div class="progress" v-for="elem in elems" >
         <div :style="{'background-color': elem.color}" class="progress__ball" > 
            <div :style="{'color': elem.numberColor}" class="progress__ball__number" > {{elem.number}} </div>
            
         </div>
        <div :style="{'background-color': elem.lineColor, display: elem.display}" class="progress__ball__line" > 
            <div :style="{display: elem.shotLine}" class="progress__ball__line__blue"></div>
        </div> 
        
    </div>

</div>  
</template>


<script>
    
    export default {
        props: {
            elems: {
                type: Array,
                required: true
            } 
        }
}


</script>



<style scoped>
.progress {
    min-width: 34px;
    height: 34px;
    display: flex;
    justify-content: start;
    align-items: center;
}
.progress__ball {
    width: 34px;
    height: 34px;
    border-radius: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
.progress__ball__number {
    font-weight: 500;
    font-size: 16px;
}
.progress__ball__line {
    margin-left: 18px;
    border-radius: 40px;
    width: 98px;
    height: 6px;
    position: relative;
    
}
.progress__ball__line__blue {
    display: block;
    position: absolute;
    left: 0px;
    border-radius: 40px;
    width: 49px;
    height: 6px;
    background: #4A3AFF;
    
}
.progress-bar {
  width: 539px;
  height: 34px;
  display: flex;
  justify-content: space-between;
  margin: 0px auto 33px;
}
@media(max-width: 1199px) {
.progress-bar {
    width: 439px;
}
.progress__ball {
    width: 31px;
    height: 31px;
}
.progress__ball__line {
    width: 74px;
}
.progress__ball__line__blue {
    width: 37px;
}
}

@media(max-width: 987px) {
.progress-bar {
    width: 379px;
}
.progress__ball {
    width: 31px;
    height: 31px;
}
.progress__ball__line {
    margin-left: 8px;
    width: 68px;
}
.progress__ball__line__blue {
    width: 39px;
}
}
@media(max-width: 575px) {
.progress-bar {
    width: 319px;
}
.progress__ball__line {
    margin-left: 6px;
    width: 50px;
}
.progress__ball__line__blue {
    width: 25px;
}
.progress__ball {
    width: 29px;
    height: 29px;
}

}
@media(max-width: 459px) {
.progress__ball__number {
    font-size: 14px;
}
}
</style>
