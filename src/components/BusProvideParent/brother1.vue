<template>
    <div>
        <button @click="sendMsg()">click me child1</button>
    </div>
</template>

<script>
    export default {
        inheritAttrs: false,
        name: 'child1',
        methods: {
            sendMsg () {
                this.$parent.$emit('child1', 'msg from child1');
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>