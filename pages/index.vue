<script setup lang="ts">
import Counter from '../../vue/src/components/counter.vue'
</script>

<template>
    <!-- {{ console.log("Render: App") }} -->
    <Counter :initialValue="80" :maxValue=10 :recurse="true" />
</template>
