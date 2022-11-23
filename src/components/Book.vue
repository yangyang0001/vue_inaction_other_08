<template>
    <div class="book-container">
        <!-- 标题-->
        <div class="title-box">
            <slot name="title"></slot>
        </div>

        <!-- 内容 -->
        <div class="content-box">
            <!-- <slot name="content" message="hello vue.js"></slot> -->
            <slot name="content" v-for="book in books" :book="book"></slot>
        </div>

        <!-- 底部 -->
        <div class="footer-box">
            <slot name="footer"></slot>
        </div>
    </div>
</template>

<script>
export default {

    data() {
        return {
            books: [
                {
                    name: '《 Vue.js 实战》',
                    author: '梁澈'
                },
                {
                    name: '《 JavaScript 语言精粹》',
                    author: 'Douglas Crockford'
                },
                {
                    name: '《 JavaScript 高级程序设计》',
                    author: 'Nicholas C. Zakas'
                },
            ]
        };
    },

    mounted() {

    },

    methods: {

    },
};
</script>

<style lang="less" scoped>
.book-container {
    >div {
        min-height: 100px;
    }

    .title-box {
        background-color: antiquewhite;
    }

    .content-box {
        background-color: aquamarine;
    }

    .footer-box {
        background-color: lightcoral;
    }
}
</style>