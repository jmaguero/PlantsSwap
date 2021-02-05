<template>
<div class="main-div bg-img"> 
  <div class="w-6/12 m-auto">
      <h1>This is your opportunity to save the world</h1>
      <p>Plants reduce the CO2 and give us the necessary O2 to survive</p>
      <p>Can you believe there's people that throw away a plant because they dont want it anymore?</p>
      <p>Well, we're here to solve this issue and many more...</p>
      <p>Do you have a plant you don't want to keep it?</p>
      <p>We will find someone else looking for that pretty little thing...</p>
  </div>    
    
  <div class="w-3/12 m-auto">
  <div class="form-group">"</div>
        <form class="flex flex-col">
        <label for="pname">Plant name:</label>
        <input type="text" name="pname" id="" placeholder="Does it has one?">
        <label for="pname">Indoor/Outdoor</label>
        <input type="text" name="int/out" id="">
        <select id="inout" name="int/out">
        <option value="indoor">Indoor</option>
        <option value="outdoor">Outdoor</option>
        </select>
      <label for="picture">Upload a picture:</label>
      <input type="file" id="picture" name="picture" multiple><br><br>
      <input type="submit">
      </form>
  </div>
</div>

</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
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