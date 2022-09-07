<script setup lang="ts" name="Son">
  import {inject} from 'vue'
    const messge = inject('messge') as {name: string, age: number}
</script>
<template>
    <div>{{messge.age}}--{{messge.name}}</div>
</template>
<style scoped></style>