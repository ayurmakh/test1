<template>
    <div>
        <button @click="findSum">{{ btnName }}</button>
    </div>
</template>

<script>
export default {
    name: 'Button',
    props: ['btnName'],
    methods: {
        findSum() {
            this.$emit('find-sum');
        }
    }
}
</script>

<style lang="scss" scoped>
    
</style>