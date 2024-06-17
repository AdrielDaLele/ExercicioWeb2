<script setup lang='ts'>
</script>

<template>
    <Card>
        <template #title><h1 class="h1-title">SelectLabel do exercicio 1</h1></template>
        <template #content>
            <slot/>
                
        <SelectLabel/>

        </template>
    </Card>
   

    
    
</template>

<style lang="scss" scoped>
.h1-title{
    font-size: 2rem;
    font-family:Arial, Helvetica, sans-serif;
}
</style>