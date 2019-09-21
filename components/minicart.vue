<template>
  <div class="minicart">
        <div class="textinminicart"><p>Итого:</p><p class="price">{{allprice}} руб.</p></div>
        <div @click="this.$emit('openclosecart')" class="buttonintocart">Моя корзина</div>
      </div>
</template>

<script>
export default {
    props: ['allprice', 'cartisactive'],
    methods: {
  }
}
</script>

<style>
.buttonintocart {
  height: 60px;
  width: 160px;
  line-height: 60px;
  float: right;
  background: #F4C468;
  display: inline-block;
  text-align: center;
  cursor: pointer;
  font-weight: 300;
  font-size: 13pt;
}
.buttonintocart:hover {
  background: #FFBB38;
}
.textinminicart {
  height: 60px;
  display: inline-block;
  padding-top: 10px;
  padding-left: 30px;
}
.textinminicart p {
  opacity: 0.4;
    font-size: 11pt;
}
.price { 
  opacity: 1!important;
  font-size: 12pt!important; 
}
.minicart {
    height: 60px;
    position: fixed;
    bottom: 0;
    width: 100%;
     background: #F7D889;
}
</style>