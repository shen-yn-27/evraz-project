<template>
  <div>
    <canvas ref="canvas" width="400" height="400"></canvas>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';
import { Canvas, Rect, Circle, Text, Polygon } from 'fabric';

const canvas = ref();
onMounted(() => {
  const fabricCanvas = new Canvas(canvas.value);
  const rect = new Rect({
    left: 100,
    top: 100,
    fill: 'blue',
    width: 100,
    height: 100,
  });
  const circle = new Circle({
    top: 100,
    left: 300,
    width: 100,
    height: 100,
    fill: 'yellow',
    radius: 20,
  });

  // const polygon = new Polygon({
  //   top: 100,
  //   left: 100,
  //   width: 100,
  //   height: 100,
  //   fill: 'green',
  // });
  fabricCanvas.add(rect, circle);
  // fabricCanvas.add(polygon);


});
</script>
<style scoped>
canvas {
  border: 1px solid #ccc;
}
</style>
