<template>
    <div>
        <table>
            <tr>
                <td>编号</td>
                <td>书名</td>
                <td>作者</td>
                <td>出版社</td>
                <td>页数</td>
                <td>价格</td>
            </tr>

            <tr v-for="item in books">
                <td>{{item.id}}</td>
                <td>{{item.name}}</td>
                <td>{{item.author}}</td>
                <td>{{item.publish}}</td>
                <td>{{item.pages}}</td>
                <td>{{item.price}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name: "Book",
        data() {
            return {
                books: [
                    {
                        id: 1,
                        name: '解忧杂货店',
                        author: '东野圭吾',
                        publish: '电子工业出版社',
                        pages: 100,
                        price: 22
                    }
                ]
            }
        },
        created() {
            const _this = this
            axios.get('http://localhost:8181/book/findAll/').then(function (resp) {
             _this.books = resp.data
            })
        }
    }
</script>

<style scoped>

</style>