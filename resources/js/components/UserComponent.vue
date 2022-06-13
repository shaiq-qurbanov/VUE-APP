<template>
<div>
    <p>user component</p>
   <h1>{{ mess }}</h1>
    <h3>{{ test }}</h3>
    <ul class="ul">
        <li v-if="show" v-for="(value,user) in users">{{ user }}----------{{ value }}</li>
    </ul>
   <button v-on:click="toggleElem">click me</button>
</div>
</template>
<script>
export default {
    props: ["mess","test"],
    data(){
        return {
       show:true,    
       users: {user1:'200$',user2:'350$',user3:'600$',user4:'1500$'}
        };
    },
    methods: {
        toggleElem: function() {
        this.show = !this.show;
        }
    }
}

</script>
<style scoped>
p{
     font-family:'Times New Roman', Times, serif;
 color: chocolate;
}
h1{
    color: red;
}
.ul{
    color: rgba(45, 49, 43, 0.692);
}

</style>