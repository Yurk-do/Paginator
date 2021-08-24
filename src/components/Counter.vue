<template>
  <div id="main-container">
    <h1 id="title-counter">{{ nameTitle }}</h1>
    <div id="counter-box">
      <button class="btn-counter btn-plus" @click="counterPlus">+</button>
      <div id="display">{{ currentValue }}</div>
      <button class="btn-counter btn-minus" @click="counterMinus">-</button>
    </div>
    <button class="btn-reset" @click="counterReset">Reset</button>
  </div>
</template>
<script>
export default {
  name: "Counter",
  props: {
    inputData: {
      type: Object,
      required: false,
      default: () => {},
    },
  },
  data() {
    return {
      nameTitle: "Counter",
      startValue: 0,
      currentValue: 0,
    };
  },
  mounted() {
    console.log("inputData", this.inputData)
  },
  methods: {
    counterPlus() {
      this.currentValue += 1;
    },
    counterMinus() {
      this.currentValue -= 1;
    },
    counterReset() {
      this.currentValue = this.startValue;
    },
  },
};
</script>
<style scoped>
#main-container {
  padding-top: 80px;
  width: 500px;
  height: 400px;
  background-color: rgb(53, 48, 48);
  color: white;
  margin: 0 auto;
  border-radius: 50%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
#title-counter {
  font-size: 50px;
}
#counter-box {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.btn-plus {
  margin-left: 30px;
}

.btn-minus {
  margin-right: 30px;
}

#display {
  font-size: 150px;
}

.btn-counter {
  display: block;
  font-size: 60px;
  text-align: center;
  padding: 15px;
  width: 100px;
  border-radius: 50%;
}
.btn-reset {
  width: 30%;
  margin: 0 auto;
  padding: 7px;
  font-size: 30px;
  border-radius: 60%;
}
</style>
