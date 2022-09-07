<script lang="ts">
export default {
    props: {
        title: String
    },
    data() {
        return {
            count: 1
        }
    },
    setup() {
        console.log(1)
    },
    mounted() {
        console.log(2)
    },
    unmounted() {
        console.log(3)
    }
}
</script>
    
<template>
    <div class="me-child">
        <h1 @click="count++">{{ `${title}${count}` }}</h1>
    </div>
</template>
    
<style scoped>

</style>
    