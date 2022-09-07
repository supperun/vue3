<script lang="ts" setup>
import { onMounted, reactive, defineProps, provide } from "vue"
import MeChild from "../components/MeChild.vue"
import MeChildOne from "../components/MeChildOne.vue"
defineProps<{
    title: {
        type: string,
        default: ''
    };
}>();
provide('messge', {age: 123, name: 'po'})

onMounted(() => {
    console.log("me mount")
    meObj.name = getPageName('vue3')

})

let meObj = reactive({ name: '', ooh: false })
function getPageName(name: string): string {
    return `My first ${name} page!`
}
function showOoh(): void {
    meObj.ooh = !meObj.ooh
}
function meChildTwo(value: string) {
    console.log(value)
}
function meChildOne(value: string) {
    console.log(value)
}
</script>
<template>
    <div class="me-wrapper">
        <h1 @click="showOoh">{{meObj.name}}</h1>
        <MeChild v-if="meObj.ooh" title="ooh!"></MeChild>
        <MeChildOne one="one" @me-child-two="meChildTwo" @me-child-one="meChildOne"></MeChildOne>
    </div>
</template>
<style scoped>
.me-wrapper {
    display: flex;
    align-items: center;
    cursor: pointer;
    user-select: none;
}
</style>
