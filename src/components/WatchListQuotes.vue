<template>
    <ListQuotes/>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import ListQuotes from './ListQuotes.vue';

const WatchListQuotes = defineComponent({
    components : {ListQuotes}
});

export default WatchListQuotes;
</script>

<style>

</style>