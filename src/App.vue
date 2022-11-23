<template>
    <div class="root">
        <h1>App根组件</h1>
        <component is="Left" :books="books" style="display: none;">
            <!-- 单个 slot 使用, 又称为 默认插槽 -->
            <p>这是在Left组件内部声明的p标签</p>

            <!-- 具名槽, 单行具名槽 -->
            <h3 slot="left">name为left的插槽</h3>
            
            <!-- 多行具名槽, 用 template 包裹就OK了 -->
            <template slot="book">
                <ul>
                    <li v-for="book in books">{{book.name}} --- {{book.author}}</li>
                </ul>
            </template>
        </component>

        <component is="Book">
            <template slot="title">
                <div>
                    图书列表
                </div>
            </template>

            <template slot="content" slot-scope="props">
                <div>
                    <!-- 配合 <slot name="content" message="hello vue.js"></slot> 使用           
                        <p>{{props.message}}</p>  
                    -->

                    <!-- 配合 <slot name="content" v-for="book in books" :book="book"></slot> 
                        子组件 数据 传递给父组件的一种插槽表现形式 -->
                    <p>{{props.book.name}} --- {{props.book.author}}</p>
                </div>
            </template>

            <template slot="footer">
                <div>
                    作者: 各位翻译官!
                </div>
            </template>
        </component>

    </div>
</template>

<script>
import Left from "@/components/Left.vue";
import Right from "@/components/Right.vue";
import Book from "@/components/Book.vue";

export default {

    components: {
        Left,
        Right,
        Book
    },

    data() {
        return {
            
        };
    },

    mounted() {

    },

    methods: {

    },
};
</script>

<style lang="less" scoped>
.root {
    padding: 5px 20px 260px 20px;
    background-color: #b9bdb0;
}
</style>