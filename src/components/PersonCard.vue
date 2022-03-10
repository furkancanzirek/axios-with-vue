<template>
  <div v-if="personOvered.name" v-show="showUserCard" :style="[personOvered.gender=='male'?{'background': '#7F7FD5'}:{background: '#f971c1'}]" class="personCard">
      <img
        :src="personOvered.picture.large"
        alt=""
      />
     <h3>{{personOvered.name.first}}&nbsp;{{personOvered.name.first}}</h3>
    <span>{{personOvered.email}}</span>
    <span>{{personOvered.cell}}</span>
  </div>
</template>
<script>
export default {
  name: "PersonCard",
  props:{
      showUserCard:Boolean,
      personOvered:Object
  }
};
</script>
<style scoped>
.personCard {
  position: absolute;
  left: 15%;
  top: 30%;
  background:#81F0E5;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 15px;
  width: 250px;
  border-radius: 10px;
  overflow: hidden;
  z-index: 999;
}
span{
    margin: 5px;
    font-size: 13px;
}
h3 {

  margin-top: 5px;
}
img{
border: 1px solid white;
border-radius: 50%;
}
</style>