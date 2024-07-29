<template>

    <form>

        <label for="rows">Filas: </label>
        <input v-model="filas" type="number" name="rows" id="rows" placeholder="Nº filas" maxlength="20" minlength="1">

        <br/>

        <label for="colums">Columnas: </label>
        <input v-model="columnas" type="number" name="colums" id="colums" placeholder="Nº columnas" maxlength="95" minlength="1">

        <div v-if="columnas > 0 && filas > 0">

            <h5>Has seleccionado {{filas}} filas y {{columnas}} columnas</h5>
            <br>
            <input @click="handleClick" type="submit" value="Enviar">

        </div>
        <div v-else>
            <h5>Selecciona una cantiddad valida de filas y columnas</h5>
        </div>

    </form>

</template>

<script lang="js" setup>

import {ref, defineEmits} from 'vue';

let columnas = ref(0);
let filas = ref(0);

const emit = defineEmits(['createTable']);

const handleClick = ()=>{

    emit("createTable", filas.value, columnas.value)
    filas.value = ""
    columnas.value=""

}

</script>

<style scoped lang="scss">

</style>