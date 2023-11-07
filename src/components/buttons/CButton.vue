<script setup lang="ts">
import { Icon } from '@iconify/vue'

defineProps<{
    label?: string
    primary?: boolean
    secundary?: boolean
}>()

</script>
<template>
    <div class="c-button">
        <div class="c-button__wrapper" :class="primary ? 'is-primary' : ''">
            <Icon v-if="secundary" icon="material-symbols-light:add" class="c-button__icon" />
            <div>{{ label }}</div>
        </div>
    </div>
</template>


<style lang="scss">
.c-button{
    display: flex;

    &__wrapper{

        display: flex;
        justify-content: center;
        align-items: center;
        padding: 5px 10px;
        border: 1px solid black;
        border-radius: 5px;
        cursor: pointer;

    }

    &__icon{
        padding-right: 8px;
    }
}
</style>