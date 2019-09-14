<template>
    <div class="popularblock">
        <div class="popularbackgroundimage"></div>
        <div class="popularaddtocart">В корзину <i class="fas fa-cart-plus"></i></div>
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

<style scooped>
    .popularblock {
        height: 280px;
        width: 196px;
        background: #fff;
        border-radius: 0 25px 25px 25px;
    }
    .popularbackgroundimage {
        width: 100%;
        height: 146px;
        background: #F7D889;
        border-radius: 0 25px 0 0;
    }
    .popularaddtocart {
        width: calc(100% - 40px);
        height: 40px;
        background: #F4C468;
        font-weight: 300;
        line-height: 40px;
        font-size: 13pt;
        padding: 0 20px;
    }
    .popularaddtocart:hover {
        background: #FFBB38;
        cursor: pointer;
    }
    .fa-cart-plus {
       float: right;
       margin-top: 12px;
    }
</style>