<script setup lang="ts">
    defineProps<{
        modelValue: string[]
    }>()
</script>
<template>
    <div class="c-list">
        <div class="c-list__wrapper" v-for="(item, index) in modelValue" :key="index">
            {{ item }}
        </div>
    </div>
</template>


<style lang="scss" scoped>
.c-list{
    display: flex;

    &__wrapper{
        border: 1px solid black;
        padding: 10px;
        padding-bottom: 20px;
        width: 250px;
        margin-right: 5px;
        margin-left: 5px;
        border-radius: 10px;
    }
}
</style>