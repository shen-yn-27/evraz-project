<template>
  <div class="Russia">
    <div class="Vietnam">
      <img src="https://cdn-icons-png.flaticon.com/512/10539/10539653.png" class="Poland">
      <h9 class="Anaxa">Газовый котёл</h9>
      <p class="Anaxnation">Температура: </p>
      <span class="Anaxnation1">{{sliderValue}}°C</span>
    </div>
    <div class="Germany">
      <h9>Коллектор</h9>
      <p>Кран кухни: </p>
      <span>{{sliderValue1}}%</span>
      <p>Кран ванной: </p>
      <span>{{sliderValue2}}%</span>
    </div>
    <div class="USSR">
      <h9>Кухня</h9>
      <p>Температура: </p>

      <span>{{sliderValue - 5 }}°C</span>
    </div>
    <div class="France">
      <h9>Ванная</h9>
      <p>Температура: </p>
      <span>{{sliderValue - 5}}°C</span>
    </div>
    <div class="China">
      <h9>Обратный коллектор</h9>
      <p>Температура: </p>
      <span>{{sliderValue}}°C</span>
    </div>
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
        v-model="sliderValue2">
      <input v-model="sliderValue2" type="number">
    </div>




  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';


const canvas = ref();

const sliderValue = ref(40);
const sliderValue1 = ref(0);
const sliderValue2 = ref(0);



</script>
<style scoped>
canvas {
  border: 1px solid #ccc;
}
.Russia{
  width: 100%;
  height: 110vh;
  position: relative;

}
.Vietnam {
  position: absolute;
  //left: 500px;
  //top: 50px;
  //width: 100px;
  //height: 150px;
}
.Anaxa{
  position: absolute;
  top: 20px;
  left: 555px;
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
  left: 500px;
  top: 500px;
  width: 100px;
  height: 150px;
  background-color: lightgreen;
  border: 2px solid black;
}
.USSR{
  position: absolute;
  left: 350px;
  top: 700px;
  width: 100px;
  height: 150px;
  background-color: cornflowerblue;
  border: 2px solid black;
}
.France{
  position: absolute;
  left: 650px;
  top: 700px;
  width: 100px;
  height: 150px;
  background-color: cornflowerblue;
  border: 2px solid black;
}
.China{
  position: absolute;
  left: 500px;
  top: 550px;
  width: 100px;
  height: 150px;
  background-color: lightgoldenrodyellow;
  border: 2px solid black;
}
.Japan{
  position: absolute;
  left: 320px;
  top: 705px;
  font-size: 11px;
}
body{
  background-color: darkgray;
}
</style>
