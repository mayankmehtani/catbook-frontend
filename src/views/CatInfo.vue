<template>
    <Card :name="name">
    </Card>
</template>

<script lang="ts">
    import Card from '../components/Card.vue';
    import axios from 'axios';

    export default {
      name: "CatInfo",
      data() {
        name: String
        return { 
          name: "a"
        }
      },
      components: {Card},
        async beforeMount () {
          let res = await axios.get("http://0.0.0.0:8000/cat/1/")
          this.name = res["data"]["name"]
          
          
          
      }
      // beforeMount(
      //   () => 
      
      // )
    }
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

