<template>
  <div class="container grid-lg my-2 py-2">

    <div class="card mb-2">
      <div class="card-header">
        <div class="h4">Acompanhando</div>
      </div>
      <div class="card-body">
        <WatchListQuotes/>
      </div>
    </div>

    <div class="card">
      <div class="card-header">
        <div class="h4">
          todas as moedas
        </div>
        <div class="card-body">
          <ListQuotes :quotes="quotes" />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent, ref,reactive, toRefs, onMounted } from 'vue';
import api from './services/api'
import ListQuotes from './components/ListQuotes.vue';
import WatchListQuotes from './components/WatchListQuotes.vue';


const App = defineComponent({
  components : {ListQuotes, WatchListQuotes},
  setup() {
    const data = reactive({
      quotes : {},
      test : ''   
     
    })

    onMounted(async() => {
      const response =  await api.all()
      data.quotes = response.data
      console.log(response.data)
    })
    
    return {...toRefs(data)}
  }
});

export default App;
</script>

<style>

</style>