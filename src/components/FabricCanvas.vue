<template>
  <div class="Russia">
    <button v-on:click="ty" class="but">{{button}}</button>
    <div class="Vietnam">
      <img src="https://cdn-icons-png.flaticon.com/512/10539/10539653.png" class="Poland">
      <h9 class="Anaxa">Газовый котёл</h9>
      <p class="Anaxnation">Температура: </p>
      <span class="Anaxnation1">{{sliderValue5}}°C</span>
    </div>
    <div class="Germany">
      <h9 class="Castorice">Коллектор</h9>
      <img src="https://cdn-icons-png.flaticon.com/512/3980/3980530.png" class="Phaenon">
      <p class="Yy">Кран кухни: </p>
      <span class="Yy1">{{sliderValue4}}%</span>
      <p class="Mydei">Кран ванной: </p>
      <span class="Jarilo">{{sliderValue3}}%</span>
    </div>
    <div class="USSR">
      <h9 class="Tt">Кухня</h9>
      <img src="https://cdn-icons-png.flaticon.com/512/963/963883.png" class="DanHeng">
      <p class="Tt1">Температура: </p>

      <span class="Tt2">{{sliderValue5 - 5 }}°C</span>
    </div>
    <div class="France">
      <h9 class="op3">Ванная</h9>
      <img src="https://cdn-icons-png.flaticon.com/512/1375/1375681.png" class="Op">
      <p class="Op2">Температура: </p>
      <span class="op4">{{sliderValue5 - 5}}°C</span>
    </div>
    <div class="China">
      <h9 class="Uy1">Обратный коллектор</h9>
      <img src="https://cdn-icons-png.flaticon.com/512/3980/3980530.png" class="Uy">
      <p class="Uy2">Температура: </p>
      <span class="Uy3">{{sliderValue5}}°C</span>
    </div>
    <div class="Ti" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Tu" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Ty" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Tr" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Te" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Tw" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="To" :class="{ 'test': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Tp" :class="{ 'A': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Ta" :class="{ 'A': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Ts" :class="{ 'B': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Td" :class="{ 'A': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Tf" :class="{ 'A': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Tg" :class="{ 'B': button === 'вкл', 'test1': button === 'выкл' }"></div>
    <div class="Th"></div>
    <div class="Tj"></div>
    <div class="Tk"></div>

  </div>
  <div>

  </div>
  <div class="Japan">
    <div class="row items-center q-gutter-sm">
      <div>Температура котла(°C): </div>
      <input
        type="range"
        min="40"
        max="80"
        value="40"
        class="slider"
        v-model="sliderValue"
      >
      <input v-model="sliderValue" type="number">
    </div>

    <div class="row items-center q-gutter-sm">
      <div>Целевая температура кухни(°C): </div>
      <input
        type="range"
        min="0"
        max="100"
        value="40"
        step="33"
        class="slider1"
        v-model="sliderValue1">
      <input v-model="sliderValue1" type="number">
    </div>

    <div class="row items-center q-gutter-sm">
      <div>Целевая температура ванной(°C): </div>
      <input
        type="range"
        min="0"
        max="100"
        value="40"
        step="33"
        class="slider2"
        v-model.lazy="sliderValue2">
      <input v-model="sliderValue2" type="number">
    </div>
  </div>
</template>
<script setup>
import { ref, watch, onMounted } from 'vue';


const canvas = ref();
let button = ref('вкл')
const sliderValue = ref(40);
const sliderValue1 = ref(0);
const sliderValue2 = ref(0);
const sliderValue3 = ref(0);
const sliderValue4 = ref(0);
const sliderValue5 = ref(0);

watch(sliderValue2, () => {
  let interval = setInterval(() => {
    if (sliderValue2.value > sliderValue3.value) {
      sliderValue3.value += 1
    }
    else if (sliderValue2.value < sliderValue3.value){
      sliderValue3.value -= 1
    }
    else {
      clearInterval(interval)
    }
  }, 100)
})
watch(sliderValue1, () => {
  let interval = setInterval(() => {
    if (sliderValue1.value > sliderValue4.value) {
      sliderValue4.value += 1
    }
    else if (sliderValue1.value < sliderValue4.value){
      sliderValue4.value -= 1
    }
    else {
      clearInterval(interval)
    }
  }, 100)
})
watch(sliderValue, () => {
  let interval = setInterval(() => {
    if (sliderValue.value > sliderValue5.value) {
      sliderValue5.value += 1
    }
    else if (sliderValue.value < sliderValue5.value){
      sliderValue5.value -= 1
    }
    else {
      clearInterval(interval)
    }
  }, 300)
})

function ty() {
  if (button.value === "вкл") {
    button.value = "выкл";
    let interval = setInterval(() => {
      if (sliderValue.value > 25){
        sliderValue.value -= 1
      }
      else {
        clearInterval(interval)
      }
    }, 300)
  }
  else {
    button.value = "вкл";
    let interval = setInterval(() => {
      if (sliderValue.value < 40) {
        sliderValue.value += 1
      }
      else {
        clearInterval(interval)
      }
    }, 300)
  }
}

</script>
<style scoped>
canvas {
  border: 1px solid #ccc;
}
.A{
  background: linear-gradient(to right, indianred, cornflowerblue);
}
.B{
  background: linear-gradient(to right, cornflowerblue, indianred);
}
.but{
  position: absolute;
  left: 545.5px;
  top: 105px;
  z-index: 3;
  height: 56px;
  width: 59px;
}
.test{
  background-color: indianred;
}
.test1{
  background-color: cornflowerblue;
}
.Ti{
  height: 10px;
  width: 130px;
  position: absolute;
  top: 150px;
  left: 625px;
}

.Tu{
  height: 180px;
  width: 10px;
  position: absolute;
  top: 150px;
  left: 755px;
}
.Ty{
  height: 10px;
  width: 110px;
  position: absolute;
  top: 320px;
  left: 650px;
}
.Tr{
  height: 220px;
  width: 10px;
  position: absolute;
  top: 389px;
  left: 607px;
}
.Te{

  height: 10px;
  width: 130px;
  position: absolute;
  top: 609px;
  left: 607px;

}

.Tw{
  height: 220px;
  width: 10px;
  position: absolute;
  top: 389px;
  left: 532px;
}

.To{
  height: 10px;
  width: 130px;
  position: absolute;
  top: 609px;
  left: 412px;
}

.Tp{
  height: 85px;
  width: 10px;
  position: absolute;
  top: 660px;
  left: 800px;
}

.Ta{
  height: 10px;
  width: 190px;
  position: absolute;
  top: 745px;
  left: 620px;
}

.Ts{
  height: 12px;
  width: 10px;
  position: absolute;
  top: 745px;
  left: 612px;
}

.Td{
  height: 85px;
  width: 10px;
  position: absolute;
  top: 660px;
  left: 320px;
}
.Tf{
  height: 10px;
  width: 215px;
  position: absolute;
  top: 745px;
  left: 320px;
}
.Tg{
  height: 12px;
  width: 10px;
  position: absolute;
  top: 745px;
  left: 533px;
}

.Th{
  background-color: cornflowerblue;
  height: 10px;
  width: 300px;
  position: absolute;
  top: 822px;
  left: 202px;
}
.Tj{
  background-color: cornflowerblue;
  height: 680px;
  width: 10px;
  position: absolute;
  top: 150px;
  left: 202px;
}
.Tk{
  background-color: cornflowerblue;
  height: 10px;
  width: 322px;
  position: absolute;
  top: 150px;
  left: 202px;
}
.Russia{
  width: 100%;
  height: 110vh;
  position: relative;

}
.Vietnam {
  position: absolute;
}
.Anaxa{
  position: absolute;
  top: 20px;
  left: 546px;
}
.Poland{
  top: 60px;
left: 500px;
  position: absolute;
  height: 150px ;
  width: 150px;
}
.Anaxnation{
  position: absolute;
  top: 220px;
  left: 510px;
}
.Anaxnation1{
  position: absolute;
  top: 220px;
  left: 610px;
}
.Germany{
  position: absolute;
}
.Phaenon{
  position: absolute;
  top: 270px;
  left: 500px;
  height: 150px;
  width: 150px;
}
.Castorice{
  position: absolute;
  top: 270px;
  left: 540px;
}
.Yy{
  position: absolute;
  top: 400px;
  left: 460px;
}
.Yy1{
  position: absolute;
  top: 400px;
  left: 500px;
}
.Mydei{
  position: absolute;
  top: 400px;
  left: 630px;
}
.Jarilo{
  position: absolute;
  top: 400px;
  left: 670px;
}
.USSR{
  position: absolute;
}
.DanHeng{
  position: absolute;
  top: 500px;
  left: 250px;
  height: 150px;
  width: 150px;
}
.Tt{
  position: absolute;

  top: 470px;
  left: 300px;
}
.Tt1{
  position: absolute;
  top: 666px;
  left: 250px;
  z-index: 3;
}
.Tt2{
  position: absolute;
  top: 666px;
  left: 345px;
  z-index: 2;
}
.France{
  position: absolute;
}
.Op{
  position: absolute;
  top: 500px;
  left: 750px;
  height: 150px;
  width: 150px;
}
.op3{
  position: absolute;
  top: 470px;
  left: 800px;
}
.Op2{
  position: absolute;
  top: 666px;
  left: 750px;
  z-index: 3;
}
.op4{
  position: absolute;
  top: 666px;
  left: 845px;
  z-index: 3;
}
.China{
  position: absolute;
}
.Uy{
  rotate: 180deg;
  position: absolute;
  top: 725px;
  left: 502px;
  height: 150px;
  width: 150px;
}
.Uy1{
  position: absolute;
  top: 700px;
  left: 530px;
}
.Uy2{
  position: absolute;
  top: 880px;
  left: 510px;
}
.Uy3{
  position: absolute;
  top: 880px;
  left: 600px;
}
.Japan{
  position: absolute;
  left: 320px;
  top: 950px;
  font-size: 11px;
}
body{
  background-color: darkgray;
}
</style>
