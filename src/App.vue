<template>
  <div class="container grid-lg">
    <input v-model="test">
    <h1>{{quotes}}</h1>
  </div>
</template>

<script lang='ts'>
import { defineComponent, ref,reactive, toRefs, onMounted } from 'vue';
import api from './services/api'

const App = defineComponent({
  setup() {
    const data = reactive({
      quotes : {},
      test : ''   
     
    })

    onMounted(async() => {
      const response =  await api.all()
      data.quotes = response.data
    })
    
    return {...toRefs(data)}
  }
});

export default App;
</script>

<style>

</style>