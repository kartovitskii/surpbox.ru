<template>
  <div class="substrate">
    <siteheader></siteheader>
    <div class="allcontent">
      <h3>Популярные</h3>
      <popular></popular>
    </div>
  </div>
</template>


<script>
import siteheader from 'vue!./header.vue'
import popular from 'vue!./popular.vue'

export default {
    data() {
      return {
      }
    },
    components: { 
      siteheader, popular 
    }
}
</script>


<style>
* {margin: 0; padding: 0;}
body {
  font-family: 'Roboto', sans-serif;
}
.substrate {
  background: #FDF7ED;
  width: 100%;
  min-height: 100vh;
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
</style>