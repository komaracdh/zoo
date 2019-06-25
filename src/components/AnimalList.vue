<template>
 <ul>
   <li v-for="(animal, index) in animals" :key="index" >
     {{animal.type}}  {{animal.name}}  {{animal.dateOfBirth ? animal.dateOfBirth : "Nepoznat"}}
    <button @click="deleteAnimal(index)" > Remove animal </button>
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
      {type:"Turtle", name:"Leonardo",dateOfBirth:""}
    ]
  }
},

methods: {
  deleteAnimal(index){
    this.animals.splice(index,1)
  }
}
}
</script>


