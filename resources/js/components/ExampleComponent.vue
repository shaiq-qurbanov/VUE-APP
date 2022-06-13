<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header" :class="{'active': active}">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                        <p>{{ message+' , '+first+', My name is  ' +name+ ' ' +lname+ ', '+what }}</p>
                        <h1>{{ name }} {{ lname }}</h1>
                        <h1>{{ what }}</h1>
                        <button v-on:click="changeUser">click me !</button>
                         <ul>
                            <li v-for="item in items">{{ item }}</li>
                         </ul>
                         <ul>
                            <li v-for="(item,index) in items">{{ item }}-{{index}}</li>
                         </ul>
                        <UserComponent :mess="name" :test="what"/>
                        <TestComponent :tst="message"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import UserComponent from './UserComponent.vue';
import TestComponent from './TestComponent.vue';
    export default {
    data() {
        return {
            message: "hello world!",
            first: "how are you?",
            name: "Boss",
            lname: "Doe",
            what: "what do you doing ?",
            active: false,
            items: ['a','b','c','d','e'],
        };
        
    },
    mounted() {
        this.show();
    },
    methods: {
        show: function () {
            console.log(this.message);
        },
        changeName: function () {
            this.name = "MEHMAN";
        },
        changelname: function () {
            this.lname = "QURBANOV";
        },
        changeUser: function () {
            this.changeName();
            this.changelname();
            this.active = !this.active;
        }
    },
    components: { UserComponent, TestComponent }
}
</script>
<style scoped>
.active{
    color:red;
}
</style>
