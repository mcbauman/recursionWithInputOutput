<script setup>
const props = defineProps(["itemKey","itemValue"]);
</script>

<template>
  <div class="fieldWrapper">
    <span>{{ props.itemKey.name }}</span>
<!-- If Object, then Recursion -->
    <BaseInput 
      v-if="(props.itemKey.type == 'Object')"
      v-for="child in props.itemKey.objectEntries"
      :itemKey="child"
      :itemValue="props.itemValue[props.itemKey.name]={}"
    />
    <input 
        type=text 
        v-else
        v-model="props.itemValue[props.itemKey.name]"
    >


<!-- AddOn To Key if Type== Number -->
  <!-- <span v-if="props.itemValue.type == 'Number'"
          >{{ props.itemValue.minRange }} - {{ props.itemValue.maxRange }}</span
        > -->

<!-- For Input Type String or Date -->
    <!-- <input
      v-if="typeof props.itemValue == 'string' || props.itemValue.type == 'Date'"
      type="text"
      class="aThird"
      v-model="props.itemValue"
    /> -->

<!-- For Input Type Number -->
    <!-- <input
      v-if="props.itemValue.type == 'Number'"
      type="Number"
      :min="props.itemValue.minRange"
      :max="props.itemValue.maxRange"
      class="aThird"
      v-model="props.itemValue"
    /> -->
<!-- For Input Type Boolean -->
    <!-- <input
      v-if="props.itemValue.type == 'Boolean'"
      type="checkbox"
      class="aThird"
      v-model="props.itemValue"
    /> -->
    
<!-- For Input Type Array -->
    <!-- <select v-if="props.itemValue.type == 'Array'" v-model="props.itemValue">
      <option v-for="option in props.itemValue.arrayOption" :value="option">
        {{ option }}
      </option>
    </select> -->
  </div>
</template>
