<template>

    <h1>Conway's - Game Of Life</h1>
    <ConwaysForm @createTable="updateTable"></ConwaysForm>

    <div id="zepa">

        <table border="1">

            <tr v-for="(index) in filas" :key="index">

                <td v-for="(index2) in columnas" :key="index2">
                    x
                </td>
                
            </tr>

        </table>

    </div>

</template>

<script lang="js" setup>

import ConwaysForm from './ConwaysForm.vue';
import {ref} from 'vue';

let filas = ref(0);
let columnas = ref(0);

function updateTable(row,col){
    filas.value = row;
    columnas.value = col;
}

</script>

<style scoped>

</style>