<template>
  <span>{{ onwNumber }}{{ dot }}{{ unit }}</span>
</template>

<script>
export default {
  name: "accumulationAnimation",
  props: {
    number: {
      type: Number,
      default: 0,
    },
    speed: {
      type: Number,
      default: 20,
    },
    maxNumber: {
      type: Number,
      default: 0,
    },
    unit: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      timer: "",
      onwNumber: 0,
      dot: "",
    };
  },
  created() {
    this.onwNumber = this.number;
    console.log(this.onwNumber);
  },
  mounted() {
    this.start();
  },
  methods: {
    // 速度分为两种，一种是定死时间，一种定死速度
    start() {
      let time = this.onwNumber;
      // 如果有小数点截取小数点进行拼接
      if (this.onwNumber.toString().includes(".")) {
        this.dot = "." + this.onwNumber.toString().split(".")[1];
      }
      if (this.maxNumber !== 0) {
        let speed = (this.maxNumber / time) * this.speed;
        this.onwNumber = 0;
        const Timer = setInterval(() => {
          this.onwNumber += 1;
          time -= 1;
          if (time < 1) {
            clearTimeout(Timer);
          }
        }, speed);
      } else {
        this.onwNumber = 0;
        const Timer = setInterval(() => {
          this.onwNumber += 1;
          time -= 1;
          if (time < 1) {
            clearTimeout(Timer);
          }
        }, this.speed);
      }
    },
  },
};
</script>

<style scoped></style>
