<script setup lang="ts">
import CButton from '../buttons/CButton.vue';
import CInput from '../forms/CInput.vue';

const props = defineProps<{
    isAdd: boolean
}>()

</script>
<template>
    <div class="c-list">
        <div >
            <slot/>
        </div>
        <div>
            <CInput vertical type="text" label="Introduzca el título"/>
            <CButton primary/>
        </div>
    </div>
</template>


<style scoped>

</style>