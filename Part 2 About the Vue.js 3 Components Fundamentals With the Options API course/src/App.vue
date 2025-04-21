<script setup>
import ClickCounter from './components/ClickCounter.vue'
import PlanComponent from './components/PlanComponent.vue'
import PlanPicker from './components/PlanPicker.vue'

const plans = [
  {
    name: 'The curious',
    price: 100,
  },
  {
    name: 'The creator',
    price: 200,
  },
  {
    name: 'The explorer',
    price: 300,
  },
]
</script>

<template>
  <h1>Hello World</h1>

  <PlanPicker />
  <ClickCounter />

  <br />
  <br />

  <PlanComponent name="The curious" />
  <PlanComponent name="The creator" />
  <PlanComponent name="The explorer" />

  <br />
  <br />

  <PlanComponent v-for="(plan, index) in plans" :name="plan.name" :key="index" />

  <br />
  <br />
  
  <PlanPicker />
</template>

<style scoped>

</style>
