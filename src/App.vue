<script setup>
import { ref } from 'vue'

const checked = ref('no')

const checkedNames = ref([])

const radioChecked = ref()

const selected = ref('')

const firstOption = ref('first option')
const secondOption = ref('second option')
</script>

<template>
  <p>Checkbox: {{ checked }}</p>
  <input type="checkbox" id="single-checkbox" v-model="checked" true-value="yes" false-value="no" />

  <p>Multiple checkbox: {{ checkedNames }}</p>
  <input type="checkbox" id="checkbox-a" v-model="checkedNames" :value="firstOption" />
  <label for="checkbox-a">A</label>
  <input type="checkbox" id="checkbox-b" v-model="checkedNames" :value="secondOption" />
  <label for="checkbox-b">B</label>
  <input type="checkbox" id="checkbox-c" v-model="checkedNames" :value="thirdOption" />
  <label for="checkbox-c">C</label>

  <p>Radio: {{ radioChecked }}</p>
  <input type="radio" id="radio-a" v-model="radioChecked" :value="firstOption" />
  <label for="a">A</label>
  <input type="radio" id="radio-b" v-model="radioChecked" :value="secondOption" />
  <label for="b">B</label>

  <p>Select: {{ selected }}</p>
  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
</template>
