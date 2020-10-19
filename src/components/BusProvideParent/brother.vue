<template>
    <div>
        <h1 v-on="$listeners">asd</h1>
        <button @click="$emit('child', 'this is payload')">click me</button>
        <grandson v-bind="$attrs"></grandson>
    </div>
</template>

<script>
import Grandson from '@/components/BusProvideParent/grandson.vue'
    export default {
        inheritAttrs: false,
        components: {
            Grandson
        },
        name: 'child',
        mounted () {
            this.$parent.$on('child1', (e) => {
                console.log(e);
            })
        }
    }
</script>

<style lang="scss" scoped>

</style>