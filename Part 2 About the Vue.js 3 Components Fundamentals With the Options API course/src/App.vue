<script setup>
import ClickCounter from './components/ClickCounter.vue'
import PlanComponent from './components/PlanComponent.vue'
import PlanPicker from './components/PlanPicker.vue'
import PostListing from './components/ChildtoParent/Lisitng.vue'


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
  <h1>Pass Data from Child to Parent</h1>
  <br />
  <br />
  <PostListing />

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

  <br />
  <br />

</template>

<style scoped>

</style>
