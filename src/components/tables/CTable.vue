<script setup lang="ts">
import { reactive, ref } from 'vue';
import CButton from '../buttons/CButton.vue';
import CInput from '../forms/CInput.vue';
import { Icon } from '@iconify/vue';
import { ErrorMessageInput } from '../../composables/types';
import CList from './CList.vue'

defineProps<{
    isAdd: boolean
}>()

defineEmits<{
    (e: 'added', value: boolean): void
}>()

const list = ref<string[]>([])

const inputString = ref('')

const isStringRepeat = ref(false)

const inputMessageError = reactive<ErrorMessageInput>({
    isError: isStringRepeat.value,
    message: 'Ya existe en la lista'
})

const addToList = () => {
    if(list.value.includes(inputString.value)){
        isStringRepeat.value = true
        return
    }
    list.value.push(inputString.value)

    inputString.value = ''
    
    isStringRepeat.value = false
}

</script>
<template>
    <div class="c-table">
        <div >
            <slot/>
        </div>
        <div v-if="isAdd" class="c-table__wrapper-form">
            <CInput v-model="inputString" :error-message="inputMessageError" vertical type="text" label="Introduzca el título"/>            
            <div class="c-table__wrapper-buttons">
                <CButton primary label="Añadir lista" @click="addToList" class="c-table__btn-add"/>
                <Icon icon="material-symbols-light:close-small-rounded" width="30" class="c-table__btn-close"
                @click="$emit('added', false)"
                />
            </div>
        </div>
        <template v-if="list.length">
            <CList
            v-model="list"
            />            
        </template>
    </div>
</template>


<style lang="scss">
.c-table{
    display: flex;
    &__wrapper-buttons{
        display: flex;
        align-items: center;
    }
    &__btn-add{
        margin-right: 5px;
    }
    &__btn-close{
        cursor: pointer;
    }
}
</style>