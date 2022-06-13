<template>
<div>
    <div class="card-header" :class="{'active':active}">test component</div>
    <h2>{{ text }}</h2>
    <h3 >{{ tst }}</h3>
    <ol>
        <li v-for="(value,book) in books">{{ book }}----{{ value }}</li>
    </ol>
    <button v-on:click="ChangeText">click</button>
</div>
</template>
<script>
export default{
    props: ["tst"],
    data() {
        return{
            text:'cnbvnbmnn',
            active:false,
            books: {book1:'hhgg',book2:'kjkjhj',book3:'ccbv'}
        };
    },
    methods: {
        ChangeText: function() {
            this.text = 'successfully';
            this.active = !this.active;
        }
    }
}
</script>
<style scoped>
.active{
    color:red;
}
</style>