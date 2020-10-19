<template>
    <div>
        <h1>组件通信</h1>
        <child @child="child" :msg='parentMsg'></child>
        <child-a :msg='parentMsg'></child-a>
    </div>
</template>

<script>
import Child from '@/components/BusProvideParent/brother.vue'
import ChildA from '@/components/BusProvideParent/brother1.vue'
    export default {
        provide() {
            return {
                foo: 'sdfdsdfd',
            }
        },
        components: {
            Child,
            ChildA
        },
        name: 'father',
        mounted: () => {
        },
        methods: {
            child: (e) => {
                console.log('this is', e);
            },
        },
        data() {
            return {
                parentMsg: 'this is parent msg'
            }
        }

    }
</script>

<style lang="scss" scoped>

</style>