<template>
 <div>
   <form @submit.prevent="addAnimals">
     <div>
       <label for="type">Type: </label>
       <input type="text" id="type" v-model="newAnimal.type" >
     </div>
     <div>
       <label for="name">Name: </label>
       <input type="text" id="name" v-model="newAnimal.name" >
     </div>
     <div>
       <label for="dateOfBirth">Date of birth: </label>
       <input type="text" id="dateOfBirth" v-model="newAnimal.dateOfBirth" >
     </div>
     <div>
       <button type="submit">Add Animal</button>
     </div>
   </form>
 
 
 <ul>
   <li v-for="(animal, index) in animals" :key="index" >
     {{animal.type}}  {{animal.name}}  {{animal.dateOfBirth ? animal.dateOfBirth : "Nepoznat"}}
    <button @click="deleteAnimal(index)" > Remove animal </button>
    <button @click="moveToTop(index)"> Move to top </button>
   </li>
 </ul>
 </div>
</template>

<script>
export default {
data(){
  return {

    newAnimal:{
      type:"",
      name:"",
      dateOfBirth:""
    },

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
  },
  moveToTop(index){
let  animalsCopy = this.animals[index]
this.animals.splice(index,1)
this.animals.unshift(animalsCopy)
  },

  addAnimals(){
    this.animals.push({...this.newAnimal})
    this.newAnimal = {
      type: "",
      name: "",
      dateOfBirth:""
    }
  }
}
}
</script>


