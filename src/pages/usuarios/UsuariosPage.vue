
<script setup lang="ts">
import { ref } from 'vue';
import UsuariosLista from './widgets/UsuariosLista.vue';
import { useUsers } from '../users/composables/useUsers';
import {User} from '../users/types';
import { useModal, useToast } from 'vuestic-ui';
const { users, isLoading, filters, sorting, pagination, ...usersApi } = useUsers()
</script>
<template>
  
  <h1 class="page-title"> Usuarios</h1>
  <div>
    <VaCard>
      <VaCardContent>
        <div class="flex flex-col md:flex-row gap-2 mb-2 justify-between">
        <div class="flex flex-col md:flex-row gap-2 justify-start">
          <VaButtonToggle
            v-model="filters.isActive"
            color="background-element"
            border-color="background-element"
            :options="[
              { label: 'Active', value: true },
              { label: 'Inactive', value: false },
            ]"
          />
          <VaInput v-model="filters.search" placeholder="Buscar">
            <template #prependInner>
              <VaIcon name="search" color="secondary" size="small" />
            </template>
          </VaInput>
        </div>
        <VaButton >Agregar Usuario</VaButton>
      </div>
      </VaCardContent>
      <UsuariosLista
      v-model:sort-by="sorting.sortBy"
      v-model:sorting-order="sorting.sortingOrder"
      :usuario="users"
      :loading="isLoading"
      :pagination="pagination"
    />
    </VaCard>

  </div>
</template>

