<script setup lang="ts">
import Counter from '../../vue/src/components/counter.gen.vue'
import Item from '../../vue/src/components/item.vue'

let id = 0
const items = ref<{ id: number; text: string }[]>([])

function addItem({ target }: KeyboardEvent) {
    if ((<HTMLInputElement>target).value) {
        items.value.push({ id: id++, text: (<HTMLInputElement>target).value });
        (<HTMLInputElement>target).value = ""
    }
}

function removeItem(rid: number) {
    items.value = items.value.filter(({ id }) => id !== rid)
}
</script>

<template>
    <section id="todo">
        <label>
            <h2>Add new item</h2>
            <input id="input" @keyup.enter="addItem" />
        </label>
        <ul class="list">
            <Item v-for="item in items" :key="item.id" :item="item" :remove="removeItem" />
        </ul>
    </section>
    <section id="counters">
        <Counter :initialValue="50" :maxValue=5 :recurse="false" />
    </section>
</template>

<style>
input {
    width: 100%;
}

.list {
    padding-inline-start: 0;
}

#counters {
    height: 10vh;
}

#counters .counters {
    display: flex;
}
</style>
