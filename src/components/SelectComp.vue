<script>
import { store } from '../store'

export default{
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container p-3 w-50">
        <select class="form-select" aria-label="Default select example" v-model="store.valoreSelect" @change="$emit('ricercaArchetipo')">
            <option v-for="(element, index) in store.arrayArchetype" :value="element.archetype_name" :key="index">{{ element.archetype_name }}</option>
        </select>
    </div>
</template>

<style>
    
</style>