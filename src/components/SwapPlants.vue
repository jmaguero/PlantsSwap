<template>
  <div class="main-div bg-img">
    <div class="w-6/12 m-auto">
      <h1>This is your opportunity to save the world</h1>
      <p>Plants reduce the CO2 and give us the necessary O2 to survive</p>
      <p>
        Can you believe there's people that throw away a plant because they dont
        want it anymore?
      </p>
      <p>Well, we're here to solve this issue and many more...</p>
      <p>Do you have a plant you don't want to keep it?</p>
      <p>We will find someone else looking for that pretty little thing...</p>
    </div>

    <div class="w-3/12 m-auto">
      <form class="flex flex-col" id="plant-signup" @submit.prevent="onSubmit">
        <label class="label" for="pName">Plant name:</label>
        <input
          type="text"
          class="form-control"
          name="pName"
          v-model= "pName"
          placeholder="Does it has one?"
        />

        <label class="label" for="pEnv">Plant type:</label>
        <input
          type="text"
          class="form-control"
          name="pEnv"
          v-model= "pEnv"
          placeholder="Indoor/Outdoor"
        />

        <label class="label" for="wPot">With or without pot:</label>
        <input
          type="text"
          class="form-control"
          name="wPot"
          v-model= "wPot"
          placeholder="Yes/No"
        />

        <h1>The name you wrote is: </h1>

       <input type="submit" @click="onSubmit" />
      </form>
    </div>
  </div>
</template>

<script>
import { ref  } from 'vue';

export default {
  name: 'addYourPlant',
  props: {
  },
  
  setup() {
    let pName = ref('Plantita');
    let pEnv = ref ('Indoor');
    let wPot = ref ('Yes');
    let planta = ref ({});
    
    function onSubmit() {
      
        planta = JSON.stringify({
        PlantName : pName.value, 
        Environment : pEnv.value,
        Pot : wPot.value 
        });


      console.log(planta);

      fetch('https://crudcrud.com/api/0bde8dae745040b8a0169cf3a228052e/plantas', {
      method: 'POST',
      body: planta,
        headers: {
      'Content-type': 'application/json; charset=UTF-8',
      },
      })
      .then(function(response) {
        return response.json(console.log(response));
      })
      .then(function(data) {
        console.log();
      });

      
    }

    return {
      pName,
      onSubmit,
      pEnv,
      wPot,
      planta
    }
  }
}
</script>

<style scoped>
.bg-img {
  background-image: url("/src/assets/plants.png");
  height: 100%;
  background-repeat: no-repeat;
  object-fit: fill;
}
.main-div {
  height: 80vh;
}
a {
  color: #42b983;
}
</style>
