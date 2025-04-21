<script setup>
const props = defineProps(
    [
        'name'
    ]
);
</script>

<template>
    <div class="plan">
        <div class="description">
            <span class="title">
                {{ name }}
            </span>
        </div>
    </div>
</template>

<style scoped>
.plan {
  background-color: white;
  padding: 15px;
  margin-bottom: 15px;
  border-radius: 8px;
  cursor: pointer;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s;
}

.plan:hover {
  transform: translateY(-3px);
}

.title {
  font-weight: bold;
  color: #333;
  font-size: 1.1rem;
}
</style>