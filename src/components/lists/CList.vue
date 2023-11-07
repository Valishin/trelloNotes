<script setup lang="ts">
import CInput from '../forms/CInput.vue';

const props = defineProps<{
    isAdd: boolean
}>()

</script>
<template>
    {{ isAdd }}
    <div class="c-list">
        <div>
            <slot/>
        </div>
        <div>
            <CInput vertical type="text" label="Introduzca el título"/>
        </div>
    </div>
</template>


<style scoped>

</style>