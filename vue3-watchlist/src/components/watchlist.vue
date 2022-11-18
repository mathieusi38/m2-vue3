<script setup>
import { ref } from 'vue'
defineProps(['series','season','episode', 'timeCursor', 'title' ])


</script>

<template>

<div class="courses-container">
    <div class="course">
        <div class="course-preview">
            <h6>Saison {{season}}</h6>
            <h2>{{series}}</h2>
        </div>
        <div class="course-info">
            <h6>ep: {{episode}}</h6>
            <h2>{{title}}</h2>
            <button class="btn"  @click="$emit('titleProgess', title)">Continue</button>
        </div>
    </div>
</div>

</template>

<style scoped>

</style>
