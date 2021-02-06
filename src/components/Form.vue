<template>
 <div class="add">
        <h3>Addition Calculator</h3>
        <form id="sum">
            <input type="text" class="form-control" v-model="pname">
            <input type="text" class="form-control" v-model="num2">
            <button @click="addNumbers" type="button" class="btn btn-light">
                Add me!
            </button>
        </form>
        <p><strong>Sum:</strong> {{ sum }}</p>
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    name: 'AddComposition',
    setup() {
        let pname = ref('Carolina');
        let num2 = ref(0);
        let sum = ref(0);
        function addNumbers() {
            sum.value = parseInt(num1.value) + parseInt(num2.value);
        }
        return {
            pname,
            num2,
            sum,
            addNumbers
        }
    }
}
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
