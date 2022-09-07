<script setup lang="ts" name="MeChildOne">
import { onMounted, reactive, defineProps, ref, type Ref, } from "vue"
import Son from "./son.vue"
defineProps<{
    one: string;
}>()
const emit  = defineEmits(['meChildTwo'])
const meOne = reactive({ two: 'two' })
let meTwo: Ref<string> = ref('meTwo')
onMounted(() => { })
function meTwoChange(): void {
    meTwo.value = "meTwoTwo"
    emit('meChildTwo', meTwo.value)
}
</script>
<template>
    <h1>
        <div @click="$emit('meChildOne', meOne.two)">{{meOne.two}}</div>
        <div @click="meTwoChange()">{{meTwo}}</div>
    </h1>
    <Son></Son>
</template>
<style scoped>

</style>