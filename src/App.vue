<template>
  <div id="app" class="wrapper">
    <Labels :rows="rows" @num-input="numInput"/>
    <Button :btn-name="btnName" @find-sum="findSum"/>
  </div>
</template>

<script>
import Labels from './components/Labels.vue'
import Button from './components/Button.vue'

export default {
  name: 'app',
  data() {
    return {
        nums: [],
        rows: ['Первое число:', 'Второе число:'],
        btnName: 'Сложить'
      };
  },
  components: {
    Labels,
    Button
  },
  methods: {
    numInput(value, i) {
      this.nums[i] = value;
    },
    findSum() {
      for (let i = 0; i < this.nums.length; i++)
        if (!this.isNumeric(this.nums[i])) {
          alert('Вводите только числа!');
          return;
        }
      var sum = 0;
      for (let i = 0; i < this.nums.length; i++)
        sum += parseFloat(this.nums[i]);
      alert(sum);
    },
    isNumeric(n) {
      return !isNaN(parseFloat(n)) && isFinite(n);
    }
  }
}
</script>

<style lang="scss">
  .wrapper {
    margin: 0 auto;
    width: 300px;
    height: 120px;
    border: 1px solid grey;
    padding: 10px;
    text-align: center;

    label {
      font-weight: 900;
    }

    * {
      margin-top: 10px;
    }
  }
</style>
