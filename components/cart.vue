<template>
    <div class="maincart">
        <div class="headerminicart"><i class="fas farightpad fa-shopping-cart"></i>Корзина<i @click="this.$emit('openclosecart')" class="fas faclosecartpos fa-times"></i></div>
        <cartitem
        @deleteitemincart="deleteitemincart"
        :cartarray="cartarray"
        v-for="cartarray in cartarray"
        :key="cartarray.id"
        ></cartitem>
    </div>
</template>

<script>
import cartitem from "vue!./cartitem.vue";
export default {
    data() {
        return {
            
        }
    },
    components: {
    cartitem
  },
  props: ['cartarray'],
  methods: {
      deleteitemincart(index) {
          this.$emit('deleteitemincart', index)
      }
  }
}
</script>

<style>
.maincart {
    position: absolute;
    width: 100%;
    min-height: 100%;
    top: 0;
    left: 0;
    background: #F7D889;
    z-index: 100;
}
.headerminicart {
    height: 76px;
    width: 100%;
    line-height: 76px;
    background: #F4C468;
    padding: 0px 30px;
    font-size: 15pt;
    color: #302614;
}
.farightpad {
    padding-right: 25px;
}
.cartinv {
    display: none;
}
.faclosecartpos {
    position: absolute;
    right: 30px;
    top: 23px;
    font-size: 25pt;
    cursor: pointer;
}
</style>