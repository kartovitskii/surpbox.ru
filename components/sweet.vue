<template>

    <div class="sweetblock">
        <div class="sweetblockimg"></div>
        <div style="padding: 0 10px; display: inline-block; width: calc(100% - 145px); float: right;">
        <p class="sweetblockname">Surpbox</p>
        <p class="sweetblockfullname">Sweet Mini</p>
        <p class="sweetblockprice">799 рублей</p>
        </div>
        </div> 
    <div class="sweetblockaddtocart">В корзину <i class="fas addcarticon addcarticonpos fa-cart-plus"></i></div>
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
.sweetblockprice {
    font-size: 11pt;
        opacity: 0.65;
        margin-top: 3px;
}
.sweetblockname {
    font-size: 12pt;
    font-weight: 300;
    margin-top: 10px;
}
.sweetblockfullname {
    margin-top: -3px;
    margin-bottom: 8px;
    font-size: 14pt;
    text-decoration: underline;
}
    .sweetblock {
        width: 100%;
        height: 122px;
        background: #fff;
        margin-bottom: 25px;
        border-radius: 0 25px 0 25px;
    }
    .sweetblockimg {
        height: 122px;
        width: 122px;
        background: #F7D889;
        display: inline-block;
    }
    .sweetblockaddtocart {
        width: calc(170px - 40px);
        height: 40px;
        background: #F4C468;
        border-radius: 0 0 10px 0;
        position: absolute;
        right: 10px;
        margin-top: -56px;
        padding: 0 20px;
        line-height: 40px;
        cursor: pointer;
        font-weight: 300;
        font-size: 13pt;
    }
    .sweetblockaddtocart:hover {
        background: #FFBB38;
    }
    .addcarticonpos {
       display: inline-block;
       height: 48px;
       line-height: 18px;
    }
</style>