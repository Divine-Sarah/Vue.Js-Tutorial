<template>
<div>
  <SearchInput @newTerm = "handleNewTerm"></SearchInput>
  <Videos v-bind:videos="videos"></Videos>
  
</div>
</template>

<script>
import SearchInput from './components/SearchInput.vue';
// eslint-disable-next-line no-unused-vars
const API_KEY = "28665302-3b288c392c1305ec248edddab";
import Videos from './components/videos.vue'
export default {
  name: 'App',
  components: { 
    SearchInput,
    Videos,
  },
  data(){
    return{
      videos:[]
    }
  },
  methods:{
    handleNewTerm: async function (searchInput){
      const response = await  fetch('https://pixabay.com/api/videos/?' + 
        new URLSearchParams({
          key: API_KEY,
          q: searchInput
        }))

        const data = await response.json();
        this.videos = data.hits;

      },
  },
};
</script>

<style>

</style>
