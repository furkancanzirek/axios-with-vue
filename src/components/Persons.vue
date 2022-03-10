<template>
  <div
    @mouseenter="$emit('person-over',person)"
     @mouseleave="$emit('person-overend')"
    :key="person.id"
    v-for="person in persons"
    :class="[person.gender === 'female' ? 'female' : 'male', 'persons']"
  >
    <Person :person="person" />
  </div>
</template>

<script>
import Person from "./Person.vue";
export default {
  name: "Persons",
  props: {
    persons: Array,
  },
  components: {
    Person,
  },
  methods: {},
};
</script>

<style scoped>

.persons {
  width: 100%;
  display: flex;
  justify-content: center;
  cursor: pointer;
border-bottom: 1px solid black;
border-right: 1px solid black;
margin: 5px;
border-radius: 10px;
-webkit-box-shadow: 4px 4px 18px -2px rgba(0,0,0,0.33);
-moz-box-shadow: 4px 4px 18px -2px rgba(0,0,0,0.33);
box-shadow: 4px 4px 18px -2px rgba(0,0,0,0.33);
transition: all 0.5s ease;
}
.persons:hover{
   box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
   transform: scale(1.03);
}
.male {
background: #7F7FD5;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #91EAE4, #86A8E7, #7F7FD5);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #91EAE4, #86A8E7, #7F7FD5); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
.female {
background: #f953c6;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #b91d73, #f953c6);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #b91d73, #f953c6); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}
</style>