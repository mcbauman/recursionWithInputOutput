<script setup>
import { ref } from "vue";
import BaseInput from "./BaseInput.vue";
const response=[
  {
    _id: "646cc341d602bc6470fcb81a",
    name: "Typ",
    type: "Array",
    arrayOption: [
      "Kunde",
      "Liferant"
    ],
    objectEntries: []
  },
  {
    _id: "645e1044d4314d4a44b7b805",
    name: "Frima",
    type: "String",
    arrayOption: [],
    objectEntries: [],
    index: 0
  },
  {
    _id: "6461eff8c66ef2415c818e0f",
    name: "Straße",
    type: "String",
    arrayOption: [],
    objectEntries: [],
    index: 1
  },
  {
    _id: "6461f006c66ef2415c818e14",
    name: "Hausnummer",
    type: "Number",
    minRange: 0,
    maxRange: 1000,
    arrayOption: [],
    objectEntries: [],
    index: 2
  },
  {
    _id: "6461e4e2c66ef2415c818dc5",
    name: "Mitarbeiter",
    type: "Object",
    arrayOption: [],
    objectEntries: [
      {
        name: "name",
        type: "String"
      }
    ],
    index: 3
  }
]
const keys=ref(response)
const values=ref({})
console.log(keys.value);

function storenNewValue(){
  console.log(values.value);
}
</script>

<template>
  <BaseInput v-for="itemKey in keys" :itemKey="itemKey" :itemValue="values"/>
  <button @click="storenNewValue">SAVE</button>
</template>

<style>

</style>
