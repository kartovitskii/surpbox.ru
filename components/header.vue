<template>
    <div class="header">
        <a class="imglink" href="/">
            <div class="logo"></div>
        </a>
        
        <div class="logotext">
            <p class="mainlogotext">SURPBOX</p>
            <p class="sublogotext">Коробочки с сюрпризами</p>
        </div>
        <div @click="menuopen()" class="burgermenu">
<svg class="ham hamRotate ham4" viewBox="0 0 100 100" width="80" onclick="this.classList.toggle('active')">
  <path
        class="line top"
        d="m 70,33 h -40 c 0,0 -8.5,-0.149796 -8.5,8.5 0,8.649796 8.5,8.5 8.5,8.5 h 20 v -20" />
  <path
        class="line middle"
        d="m 70,50 h -40" />
  <path
        class="line bottom"
        d="m 30,67 h 40 c 0,0 8.5,0.149796 8.5,-8.5 0,-8.649796 -8.5,-8.5 -8.5,-8.5 h -20 v 20" />
</svg>
        </div>
    </div>
    <menu :class="menuisactive ? '' : 'menu'"></menu>
</template>


<script>
import menu from 'vue!./menu.vue'

export default {
    data() {
      return {
          menuisactive: false
      }
    },
    components: { 
      menu
    },
     methods: {
          menuopen() {
                  this.menuisactive =! this.menuisactive
          }
      }
}
</script>


<style>
.header {
    height: 76px;
    background: #fff;
    padding: 0px 20px;
}
.logo {
    width: 76px;
    height: 76px;
    background: url('https://surpbox.ru/dist/img/logomin.svg') no-repeat;
    background-size: 45px;
    background-position: 0% 50%;
    display: inline-block;
}
.logotext {
    display: inline-block;
    position: absolute;
    top: 22px;
    left: calc(50% - 70px);
    text-align: center;
}
.mainlogotext {
    font-size: 15pt;
}
.sublogotext {
    font-size: 9pt;
    font-weight: 200;
    margin-top: -5px;
}
.burgermenu {
    float: right;
    width: 80px;
    position: relative;
    right: -22px;
    cursor: pointer;
    z-index: 100;
}
.menu {
    display: none;
}
.ham {
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
  transition: transform 400ms;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
  position: relative;
  top: -2px;
  opacity: 0.9;
}
.hamRotate.active {
  transform: rotate(45deg);
}
.hamRotate180.active {
  transform: rotate(180deg);
}
.line {
  fill:none;
  transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
  stroke:#000;
  stroke-width:5.5;
  stroke-linecap:round;
}
.ham4 .top {
  stroke-dasharray: 40 121;
}
.ham4 .bottom {
  stroke-dasharray: 40 121;
}
.ham4.active .top {
  stroke-dashoffset: -68px;
}
.ham4.active .bottom {
  stroke-dashoffset: -68px;
}
</style>