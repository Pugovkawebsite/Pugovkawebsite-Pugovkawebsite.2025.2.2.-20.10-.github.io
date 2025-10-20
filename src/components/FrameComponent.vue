<template>
<div class="frame">
    <slot></slot>
</div>

  
</template>






<style scoped>
.frame {
    border: 1px solid #D9DBE9;
    border-radius: 34px;
    width: 698px;
    height: 606px;
    box-shadow: 0 5px 16px 0 rgba(8, 15, 52, 0.06);
    padding: 32px 50px 80px 50px;
    margin-bottom: 31.61px;
    position: relative;
}

@media(max-width: 1199px) {
.frame {
  width: 598px;
  height: 506px;
}

}
@media(max-width: 987px) {
.frame {
  width: 498px;
}
}
@media(max-width: 767px) {
.frame {
  width: 458px;
  height: 506px;
  padding: 32px 35px 60px 35px;
}
}
@media(max-width: 575px) {
.frame {
    width: 418px;
    padding: 32px 30px 50px 30px;
}
}
@media(max-width: 459px) {
.frame {
  width: 370px;
  padding: 32px 20px 50px 20px;
}
}
</style>
