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
      <footer @click="hm()" style="font-size: 8pt; text-align: center; padding-bottom: 10px; opacity: 0.3">
      <p>
      surpbox.ru - магазин коробочек с сюрпризами<br>
      ИП Картовицкий И.И. ОГРН 5683832823998</p>
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
 var cooka = this.readCookie('cart') // тут я объявил переменную для кук с корзиной
 if (cooka.length > 0) { // проверяем есть ли в куке че нить
    console.log(JSON.parse(this.readCookie('cart'))) // выведем массив в консоль с куками
var json_data = JSON.parse(this.readCookie('cart')) // тут тип присваем переменной кукки в виде нормальном
for (var i=0; i < json_data.length; i++) { // перебираем куку и разбиваем на классы (объекты)
  this.cartarray.push({'name':json_data[i].name, 'price':json_data[i].price});  // пушим в массив с остальными объектами корзины
  this.calcsum() // сумму в корзине считаем
  }
  console.log(this.readCookie('cart')) // хуйня какая то хз зачем делал
 } else {
   console.log('кука пустая') // а тут тип куки нет
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
      readCookie(name){
var bOut = false;
return unescape(document.cookie.replace(/([^ ;=]+)=?([^;]+)?;?/g,function(m,n,v){
if (n==name && !bOut) {
bOut = true;
return v;
} else {
return '';
}
}));
},
      hm() {
        document.cookie = 'cart' + '=; expires=Thu, 01 Jan 1970 00:00:01 GMT;'
      },
      calcsum() {
        this.allprice = 0
        for (var i = 0; i < this.cartarray.length; i++) {
          this.allprice = this.allprice + this.cartarray[i].price
}
      },
      addtocart(name, price) {
        this.cartarray.push({
          name: 'Surpbox '+name,
          price: price
        })
       this.calcsum()
        console.log('-----------------------------')
        //this.hm()
        document.cookie = 'cart=' + JSON.stringify(this.cartarray)
        console.log(this.readCookie('cart'))
        console.log('-----------------------------')
        console.log('Итого: '+this.allprice+' рублей.')
        console.log('В корзине:')
        for (var i = 0; i < this.cartarray.length; i++) { 
        console.log(this.cartarray[i].name, this.cartarray[i].price); }
        console.log(JSON.parse(this.readCookie('cart')))
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