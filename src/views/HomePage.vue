<script setup lang="ts">
    import { ref } from 'vue';
    import CButton from '../components/buttons/CButton.vue'
    import CTable from '../components/tables/CTable.vue'

    const newList = ref(false)
</script>
<template>
    <CTable :is-add="newList" @added="e => newList = e">
        <template v-if="!newList" #default>
            <CButton label="Añadir otra lista" @click="newList = true" />
        </template>
    </CTable>
</template>


<style scoped>

</style>