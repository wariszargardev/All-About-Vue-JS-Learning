<script setup>
import PlanComponent from './PlanComponent.vue';

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
    }
]

</script>

<template>
    <h1>Plan Picker</h1>
    <PlanComponent v-for = "(plan, key) in plans" :key="key" :name="plan.name" />
    <br />
    <br />
</template>