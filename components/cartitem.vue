<template>
<div class="itemcart">
    <div class="itemcartcontent">
        {{ cartarray.name }}
        <br>
        <p>{{cartarray.price}} руб.</p>
        <p @click="this.$emit('deleteitemincart', cartarray.id)">Удалить</p>
    </div>
  </div>
</template>

<script>
export default {
props: ['cartarray']
}
</script>

<style>
.itemcart {
    height: 80px;
    width: 90%;
    border-bottom: 1px solid #F4C468;
    margin: 0 auto;
}
.itemcartcontent {
    height: 40px;
    margin-top: 10px;
    padding: 20px 10px 0 0;
    width: 100%;
}
.itemcartcontent p {
    opacity: 0.4;
    font-size: 10pt;
}
</style>