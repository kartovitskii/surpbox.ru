<template>
    <div class="substrateburgermenu">
        <div class="containerburgermenu">
            <div class="headerburgermenu"></div>
        </div>
    </div>
</template>


<script>
export default {
    data() {
      return {
        
      }
    },
     methods: {

      }
}
</script>

<style>
.substrateburgermenu {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgb(105,70,4,0.37);
    z-index: 50;
}
.containerburgermenu {
    height: 100vh;
    float: right;
    width: 290px;
    background: #F7D889;
}
.headerburgermenu {
    height: 76px;
    width: 100%;
    background: #F4C468;
}
</style>