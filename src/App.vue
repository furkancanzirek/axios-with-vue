<template>
  <PersonCard :showUserCard="showUserCard" :personOvered="personOvered"  />
     <Header />
    <div class="container">
     
      <Persons @person-over="personOver" @person-overend="personOverEnd" :persons="persons" />
    </div>
      <Button @change-users="changeUsers" />
</template>

<script>
import Header from "./components/Header.vue";
import Persons from "./components/Persons.vue";
import Button from "./components/Button.vue";
import PersonCard from "./components/PersonCard.vue";
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      persons: [],
      showUserCard:false,
      personOvered:{},
    };
  },
  created(){
    axios.get("https://randomuser.me/api/?results=5").then(response=>this.persons=response.data.results)
  },
  components: {
    Header,
    Persons,
    Button,
    PersonCard
  },
  methods:{
    changeUsers(){
      axios.get("https://randomuser.me/api/?results=5").then(response=>this.persons=response.data.results)
    },
    personOver(person){
      this.showUserCard=true
      this.personOvered=person
      console.log(person);
    },
    personOverEnd(){
       this.showUserCard=false
    }
  }
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
   height: 100vh;
   background: #F0F4EF;
   transition: all 2s ease;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-wrap: wrap;
  border-radius: 5px;
  padding: 5px;
  width: 25vw;
  min-width: 400px;
  
}
</style>
