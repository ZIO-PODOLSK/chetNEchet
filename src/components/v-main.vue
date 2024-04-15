<template>
  <div class="wrapper">
    <div class="wrapper-input">
      <div class="input_1">
        <input type="range" v-model="count_1" />
        <p>{{ count_1 }}</p>
      </div>
      <div class="input_2">
        <input type="range" v-model="count_2" />
        <p>{{ count_2 }}</p>
      </div>
    </div>
    <div class="wrapper-info">
      <p class="wrapper-info_text">{{ answer }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Slider",
  data() {
    return {
      count_1: 50,
      count_2: 50,
      answer: "null",
    };
  },
  computed: {
    chetNEchet() {
      if (this.count_1 % 2 == 0 && this.count_2 % 2 == 0) {
        this.answer = "чёт";
      } else {
        this.answer = "не чёт";
      }
    },
  },
  watch: {
    count_1() {
      this.chetNEchet;
    },
    count_2() {
      this.chetNEchet;
    },
  },
};
</script>

<style>
.input_1,
.input_2 {
  display: flex;
  justify-content: center;
  margin-left: 20px;
  margin-top: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  border: 1px solid black;
  border-radius: 10px;
  max-width: 200px;
  padding: 10px 10px 10px 10px;
}
.wrapper-info {
  border: 1px solid black;
  border-radius: 10px;
  margin-top: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  width: 300px;
  padding: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.wrapper {
  display: flex;
  justify-content: center;
}
.wrapper-info_text {
  font-size: 30px;
}
</style>