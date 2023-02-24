<template>
 <div class="app">
    <p>
      {{name}} - {{ age }}
    </p>
    <button @click="changeName('Zelda')" >Change Name</button>
    <button @click="changeAge(30)" >Change Name</button>
 </div>
  
</template>

<script lang="ts">
import { defineComponent } from 'vue';


// this is required for TS where we specify defineComponent
export default defineComponent({
  name: 'App',

  data() {
    return  {
      name: 'Link',  //TS will know this must always be a string
      // we use type assertion if we have multiple types the keyword being  as
      age:  25 as number | string
    }
  },
  methods:{
    //we need to specify the type of the arg
    changeName(name: string){
      this.name  = name
      return name
    },
    changeAge(age: string | number ){
      this.age = age
      return age
    }
  }
});
</script>

<style>

</style>
