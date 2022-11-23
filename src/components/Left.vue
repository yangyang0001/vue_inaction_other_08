<template>
    <div class="left">
        <h3>Left组件 --- count is: {{ count }}</h3>
        <!-- 单个 slot -->
        <slot></slot>

        <!-- 具名槽 -->
        <slot name="left"></slot>

        <!-- 多行具名槽 -->
        <slot name="book"></slot>
    </div>
</template>

<script>

export default {

    data() {
        return {
            count: 0,
        }
    },

    methods: {
        
    },

    mounted() {

    }

}

</script>

<style lang="less" scoped>
.left {
    float: left;
    background-color: aqua;
    padding: 5px 0px 20px 20px;
    font-weight: bolder;
    width: 48%;
}

/deep/ h5 {
    color: red;
}
</style>