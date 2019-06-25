<template>
 <ul>
   <li v-for="(animal, index) in animals" :key="index" >
     {{animal.type}}  {{animal.name}}  {{animal.dateOfBirth}}
   </li>
 </ul>
</template>

<script>
export default {
data(){
  return {
    animals: [
      {type:"Lion", name:"Mufasa",dateOfBirth:"11/11/1998"},
      {type:"Dog", name:"Buddy",dateOfBirth:"07/07/2001"},
      {type:"Bear", name:"Balu",dateOfBirth:"10/09/2005"},
      {type:"Mouse", name:"Mickey",dateOfBirth:"11/11/1931"},
      {type:"Turtle", name:"Leonardo",dateOfBirth:"04/06/2015"}
    ]
  }
}
}
</script>


