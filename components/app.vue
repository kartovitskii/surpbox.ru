<template>
  <div class="substrate">
    <siteheader></siteheader>
    <div class="allcontent">
      <h3>Популярные</h3>
      </div>
      <div class="popularblockcontainer">
      <popular @addtocart = "addtocart" :populararray="populararray" v-for="populararray in populararray"></popular>
    </div>
         <div class="allcontent">
      <h3>Сладкие</h3>
        <sweet></sweet>
        <sweet></sweet>
      </div>
      <footer style="font-size: 8pt; text-align: center; padding-bottom: 10px; opacity: 0.3">
      <p></p>
      surpbox.ru - магазин коробочек с сюрпризами<br>
      ИП Картовицкий И.И. ОГРН 5683832823998
      </footer>
      <minicart :allprice="allprice"></minicart>
  </div>
</template>


<script>
import siteheader from 'vue!./header.vue'
import popular from 'vue!./popular.vue'
import sweet from 'vue!./sweet.vue'
import aboutbox from 'vue!./aboutbox.vue'
import minicart from 'vue!./minicart.vue'

export default {
   created() { // ну тип тут мы это, из кук пушим в массив данные с корзины
var json_data = JSON.parse(document.cookie)
for (var i=0; i < json_data.length; i++) {
  this.cartarray.push({'name':json_data[i].name, 'price':json_data[i].price}); 
  for (var i = 0; i < this.cartarray.length; i++) {
          this.allprice = this.allprice + this.cartarray[i].price
        }
}   
  }, 
    data() {
      return {
        allprice: 0,
        populararray: [
      { 
        name: 'Mini',
        price: 990,
        id: 0
      },
            { 
        name: 'Sweet Original',
        price: 890,
        id: 1
      }
    ],
      cartarray: []
      }
    },
    components: { 
      siteheader, popular , sweet, minicart
    }, 
    methods: {
      addtocart(name, price) {
        console.log(name, price)
        this.cartarray.push({
          name: 'Surpbox '+name,
          price: price
        })
        this.allprice = 0
       for (var i = 0; i < this.cartarray.length; i++) {
          this.allprice = this.allprice + this.cartarray[i].price
        }
                 console.log('-----------------------------')
        var forcookie = JSON.stringify(this.cartarray)
        document.cookie = forcookie
        console.log(JSON.parse(document.cookie))
         console.log('-----------------------------')
        console.log('Итого: '+this.allprice+' рублей.')
        console.log('В корзине:')
        for (i = 0; i < this.cartarray.length; i++) { console.log(this.cartarray[i].name, this.cartarray[i].price); }
      }
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