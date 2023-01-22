<template>
    <Card :name="name" :age="age" :neuteredStatus="neuteredStatus">
    </Card>
</template>

<script lang="ts">
    import Card from '../components/Card.vue';
    import axios from 'axios';

    export default {
      name: "CatInfo",
      data() {
        return { 
          name: "",
          age: 0,
          appearance: "",
          lane: "",
          phase: "",
          neuteredStatus: "",
          dateCaught: "",
          dateNeutered: "",
          dateReleased: ""
        }
      },
      components: {Card},
      async beforeMount () {
        let res = await axios.get("http://0.0.0.0:8000/cats/1/");
        let response_data = res["data"];
        
        // information on cat
        this.name = response_data["name"];
        this.age = response_data["age_in_months"];
        this.appearance = response_data["appearance"];
        this.lane = response_data["lane"];
        
        // Neutered Information
        this.neuteredStatus = response_data["neutered"];
        this.dateCaught = response_data["date_caught"];
        this.dateReleased = response_data["date_released"];
        this.dateNeutered = response_data["date_neutered"];
      }
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

