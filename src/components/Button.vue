<template>
    <button @click="$emit('change-users')">Change Users</button>
</template>
<script>
export default {
name:'Button'    
}
</script>
<style scoped>
button{
  border: none;
  background-color: transparent;
  cursor: pointer;
  width:200px;
  height: 50px;
  padding-left: 15px;
  margin-top:15px ;
  background:#81F0E5;
  border-radius: 10px;
  font-size: 18px;
}
button:active{
  transform: scale(1.02);

}
</style>