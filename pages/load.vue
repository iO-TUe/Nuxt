<script setup lang="ts">
import Counter from '../../vue/src/components/counter.vue';
</script>

<template>
    <!-- {{ console.log("Render: App") }} -->
    <Counter :initialValue="50" :maxValue=1000 :recurse="false" />
</template>
