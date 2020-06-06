<template>

    <div> {{msg}}
        <table>
            <tr>
                <td>编号</td>
                <td>图书名称</td>
                <td>作者</td>
            </tr>
            <tr v-for="item in books">
                <td>{{item.bid}}</td>
                <td>{{item.bookname}}</td>
                <td>{{item.bookauthor}}</td>

                <!--<td>{{books[0].id}}</td>-->
                <!--<td>{{books[0].name}}</td>-->
                <!--<td>{{books[0].author}}</td>-->

            </tr>
        </table>
        <table>
            <tr>
                <td>一</td>
                <td>二</td>
                <td>三</td>
            </tr>
            <tr>
                <td>10</td>
                <td>15</td>
                <td>5</td>
            </tr>
            <tr >
                <td><input v-text="输入" ></td>
                <td>二</td>
                <td>三</td>

                <!--<td>{{books[0].id}}</td>-->
                <!--<td>{{books[0].name}}</td>-->
                <!--<td>{{books[0].author}}</td>-->

            </tr>
        </table>

    </div>

</template>

<style></style>

<script>

    export default{
        name: "Books",
        data () {
            return {
                msg: 'books',
                books: [

                ]

            }
        },
        created(){
            const axios = require('axios').default;

            const _this = this
            axios.get("http://localhost:8080/book/findAll").then(function (resp) {

                console.log(resp)
                _this.books = resp.data
            })


        }
    }

</script>
