<script setup lang="ts">
    defineProps<{
        type: string
        label?: string
        vertical?: boolean
    }>()
</script>

<template>
    <div class="c-input">
        <div class="c-input__wrapper" :class="vertical ? 'is-vertical' : ''">
            <label v-if="label" for="input">{{ label }}</label>
            <input id="input" :type="type" />
        </div>
    </div>
</template>


<style lang="scss">
.c-input{
    display: flex;
    
    &__wrapper{
        &.is-vertical{
        display: flex;
        flex-direction: column;
    }
    }
}
</style>