<template>
    <div class="popularblock">
        <div class="popularbackgroundimage"></div>
        <div @click="$emit('addtocart', populararray.name, populararray.price)" class="popularaddtocart">В корзину <i class="fas addcarticon fa-cart-plus"></i></div>
        <a class="popularblockname">{{ populararray.name }}</a>
        <p class="popularblockprice">{{ populararray.price }} рублей</p>
    </div>
</template>


<script>
export default {
    data() {
      return {
        
      }
    },
     methods: {

      },
    props: ['populararray']
}
</script>

<style>
    .popularblockname {
        margin-top: 20px;
        font-size: 15pt;
        font-weight: 400;
        text-decoration: underline;
    }
    .popularblockname,  .popularblockprice {
        width: 100%;
        padding: 0 20px;
        display: block;
        opacity: 0.85;
    }
    .popularblockprice {
        font-size: 11pt;
        opacity: 0.65;
        margin-top: 3px;
    }
    .popularblock {
        margin-left: 20px;
    }
    .popularblock {
        display: inline-block;
        height: 280px;
        width: 196px;
        background: #fff;
        border-radius: 0 25px 25px 25px;
        margin-right: 0px;
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
    .addcarticon {
       float: right;
       margin-top: 12px;
    }
</style>