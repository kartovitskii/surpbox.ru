<template>
  <div class="minicart">
        {{allprice}}
      </div>
</template>

<script>
export default {
    props: ['allprice']
}
</script>

<style>
.minicart {
    height: 60px;
    background: #F7D889;
}
</style>