<template>
  <div class="app">
    <p>{{ jobs[0].location }}</p>
    
  </div>
</template>

<script lang="ts">
import { defineComponent, ref} from "vue";
//we can import a custom type to use
import Job from './types/job'

// this is required for TS where we specify defineComponent
export default defineComponent({
  name: "App",
  setup() {
    //using reactive
    // const state = reactive({
    //   name: "Link",
    //   age: 25 as string | number,
    // });
    // state.name = 999
    // state.age  = false
    // return {
    //   ...toRefs(state),
    // };

    // if we want to use TS using ref we need to include <> and define the type after ref as ref is an object
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ])

    return {jobs}
  },
  methods: {
    
  },
});
</script>

<style></style>
