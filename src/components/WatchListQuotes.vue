<template>
    <ListQuotes :quotes="quotes" :listenQuotes="listenQuotes"/>
    <div class="mt-2 text-right">
         <cite class="text-small">
        Atualizará novamente em  <b>{{nextUpdateTime}}</b>
        </cite>
    </div>
   
</template>

<script lang='ts'>
import { defineComponent, ref } from 'vue';
import ListQuotes from './ListQuotes.vue';

const WatchListQuotes = defineComponent({
    components : {ListQuotes},
    props : {
        listenQuotes : {
            type : Array,
            required : true
        }
    },

    setup() {
        const quotes = ref({});
        const nextUpdateTime = ref(30)
        return {quotes , nextUpdateTime} 
    }
});

export default WatchListQuotes;
</script>

<style>

</style>