<template>
  <div>
    <div v-for="(row, i) in rows" :key="i">
      <label>{{ row }} </label>
      <input type="text" @input="numInput(i)" v-model="value[i]">
    </div>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      value: []
    }
  },
  name: 'Labels',
  props: ['rows'],
  methods: {
    numInput(i) {
      this.$emit('num-input', this.value[i], i);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  label {
    font-weight: 900;
  }

  * {
    margin-top: 10px;
  }
</style>