<template>
  <div>
    <vue-p5
        @preload="preload"
        @setup="setup"
        @draw="draw">
    </vue-p5>
  </div>
</template>

<script>
import VueP5 from "vue-p5";

export default {
  name: "p5-example",
  components: {
    "vue-p5": VueP5
  },
  data: () => ({
  }),
  methods: {
    setup(sketch) {
      sketch.createCanvas(720, 400);
      sketch.stroke(255);
      sketch.noFill();
    },
    draw(sketch) {
      sketch.background(0);
      for (let i = 0; i < 200; i += 20) {
        sketch.bezier(
          sketch.mouseX - i / 2.0,
          40 + i,
          410,
          20,
          440,
          300,
          240 - i / 16.0,
          300 + i / 8.0
        );
      }
    }
  }
};
</script>
