<template>
      <div>{{ message}}</div>
  <!-- Canvas -->
  <canvas id="c"></canvas>
  <!-- Add Rectangle Button -->
  <div>
    <button @click="drawRect">Add Rect</button>
    <button @click="subWidth">-</button>
    <button @click="addWidth">+</button>
  </div>
</template>

<script>
export default {
    name: 'FirstPage',
    data() {
        return {
            message: 'Vue + Canvas API',
            vueCanvas: null,
            rectWidth:200
        }
    },
    mounted() {
        var c = document.getElementById("c");
        var ctx = c.getContext("2d");
        this.vueCanvas = ctx;
    },
    methods: {
        drawRect() {
            // limpa a tela 
            this.vueCanvas.clearRect(0, 0, 400, 200);
            // desenha rect 
            this.vueCanvas.beginPath();
            this.vueCanvas.rect(20, 20, this.rectWidth, 100);
            this.vueCanvas.stroke();
        },
        addWidth() {
            this.rectWidth += 10
            this.drawRect()
        },
        subWidth() {
            this.rectWidth -= 10
            this.drawRect()
        }
    }

}
</script>

<style>
</style>