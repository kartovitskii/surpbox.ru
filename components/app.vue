<template>
  <div class="substrate">
    <siteheader></siteheader>
    <div class="allcontent">
      <h3>Популярные</h3>
      </div>
      <div class="popularblockcontainer">
      <popular :populararray="populararray" v-for="populararray in populararray"></popular>
    </div>
         <div class="allcontent">
      <h3>Сладкие</h3>
        <sweet></sweet>
        <sweet></sweet>
      </div>
      <footer @click="test()" style="font-size: 8pt; text-align: center; padding-bottom: 10px; opacity: 0.3">
      surpbox.ru - магазин коробочек с сюрпризами<br>
      ИП Картовицкий И.И. ОГРН 5683832823998
      </footer>
  </div>
</template>


<script>
import siteheader from 'vue!./header.vue'
import popular from 'vue!./popular.vue'
import sweet from 'vue!./sweet.vue'
import aboutbox from 'vue!./aboutbox.vue'

export default {
    data() {
      return {
        populararray: [
      { 
        name: 'Mini',
        price: 790,
      },
            { 
        name: 'Sweet Original',
        price: 990,
      }
    ]
      }
    },
    components: { 
      siteheader, popular , sweet
    }, 
    methods: {

    }
}
</script>


<style>
* {margin: 0; padding: 0;}
:active, :hover, :focus {
    outline: 0;
    outline-offset: 0;
}
body {
  font-family: 'Roboto', sans-serif;
  overflow-x: hidden;
}
.substrate {
  background: #FDF7ED;
  width: 100%;
}
.imglink {
  text-decoration: none;
}
.allcontent {
  padding: 0px 20px;
}
h3 {
  font-weight: 300;
  font-size: 18pt;
  margin: 20px 0px;
}
.popularblockcontainer {
  width: 100%;
  height: 290px;
  overflow-x: scroll;
  white-space: nowrap;
}
</style>