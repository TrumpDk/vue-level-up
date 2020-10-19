<template>
    <div>
        <p>{{$attrs.msg}}</p>
        <p>{{foo}}</p>
    </div>
</template>

<script>
    export default {
        inject: ['foo'],
        name: 'grandson'
    }
</script>

<style lang="scss" scoped>

</style>