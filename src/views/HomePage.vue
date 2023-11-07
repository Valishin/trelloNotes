<script setup lang="ts">
    import { ref } from 'vue';
import CButton from '../components/buttons/CButton.vue'
    import CList from '../components/lists/CList.vue'

    const newList = ref(false)
</script>
<template>
    <CList :isAdd="newList">
        <template #default>
            <CButton label="Añadir otra lista" @click="newList = true" />
        </template>
    </CList>
</template>


<style scoped>

</style>