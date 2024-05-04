<template>
    <VaDataTable :columns="columns" :items="usuario">
        <template #cell(nombreCompleto)="{ rowData }">
            <div class="flex items-center gap-2 max-w-[230px] ellipsis">
                {{ rowData.nombreCompleto }}
            </div>
        </template>
        <template #cell(correoElectronico)="{ rowData }">
            <div class="max-w-[120px] ellipsis">
                {{ rowData.correoElectronico }}
            </div>
        </template>
        <template #cell(rol)="{ rowData }">
            <div class="ellipsis max-w-[230px]">
                {{ rowData.rol }}
            </div>
        </template>

        <template #cell(actions)="{ rowData }">
            <div class="flex gap-2 justify-end">
                <VaButton preset="primary" size="small" icon="mso-edit" aria-label="Edit user" />
                <VaButton preset="primary" size="small" icon="mso-delete" color="danger" aria-label="Delete user" />
            </div>
        </template>
    </VaDataTable>
    <div class="flex flex-col-reverse md:felex-row gap-2 justify-between items-center py-2">
        <div>
            <b> Resultados</b>
            Resultados por página
        </div>
    </div>
</template>

<script setup lang="ts">
import { defineVaDataTableColumns, useModal } from 'vuestic-ui'
import { Pagination } from '../../../data/pages/projects';
const columns = defineVaDataTableColumns([
    { label: 'Nombre Completo', key: 'nombreCompleto', sortable: true },
    { label: 'Correo Electrónico', key: 'correoElectronico', sortable: true },
    { label: 'Rol', key: 'rol', sortable: true },
    { label: ' ', key: 'actions', align: 'right' },
]);
const usuario = ([
    {
        id: 1,
        nombreCompleto: 'Juan Pérez',
        correoElectronico: 'Juan@gmail.com',
        rol: 'Administrador',
    },
    {
        id: 2,
        nombreCompleto: 'María López',
        correoElectronico: 'Maria@gmail.com',
        rol: 'Usuario',
    },
    {
        id: 3,
        nombreCompleto: 'Pedro Ramírez',
        correoElectronico: 'Pedro@gmail.com',
        rol: 'Usuario',
    },
]);
//Creamos un array de usuarios


</script>
