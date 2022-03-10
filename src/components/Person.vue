<template>
    <div  class="person">
        <img v-bind:src="person.picture.thumbnail" alt="">
        <div class="name">
            <span>{{person.name.first}} &nbsp; {{person.name.last}}</span>
        </div>
    </div>
</template>
<script>
export default {
    name:'Person',
    props:{
        person:Object
    }
}
</script>
<style scoped>
    .person{
        display: flex;
        align-items: center;
        padding: 15px;
        width: 100%;
         color: #fff;
         margin: 10px;
         
    }
    .name{
        margin-left: 15px;
        font-size: 1.5em;
        font-weight: bold;
    }
    img{
        border-radius: 50%;
    }
</style>