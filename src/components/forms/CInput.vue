<script setup lang="ts">
import { ErrorMessageInput } from '../../composables/types';

    defineProps<{
        modelValue: string
        type: string
        errorMessage?: ErrorMessageInput
        label?: string
        vertical?: boolean
    }>()

    const emits = defineEmits<{
        (e: 'update:modelValue', value: unknown): void
    }>()

    const updateModelValue = (e: Event) => {
        const value: string = (e.target as HTMLInputElement).value

        emits('update:modelValue', value)
    }
</script>

<template>
    <div class="c-input">
        <div class="c-input__wrapper" :class="vertical ? 'is-vertical' : ''">
            <label v-if="label" for="input">{{ label }}</label>
            <input id="input" :type="type" :value="modelValue" @input="updateModelValue" />
            <p v-if="errorMessage?.isError">{{ errorMessage.message }}</p>
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