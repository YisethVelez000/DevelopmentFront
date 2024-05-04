<template>
  <VaForm ref="passwordForm" @submit.prevent="submit">
    <h1 class="font-semibold text-4xl mb-4">¿Olvidaste tu contraseña?</h1>
    <p class="text-base mb-4 leading-5">
      Si ha olvidado su contraseña, no se preocupe. Sólo tienes que introducir tu dirección de correo electrónico y te enviaremos un mensaje con una contraseña temporal.
    </p>
    <VaInput
      v-model="email"
      :rules="[(v) => !!v || 'Email field is required']"
      class="mb-4"
      label="Introduce tu dirección de correo electrónico"
      type="email"
    />
    <VaButton class="w-full mb-2" @click="submit">Restablecer contraseña</VaButton>
    <VaButton :to="{ name: 'login' }" class="w-full" preset="secondary" @click="submit">Volver</VaButton>
  </VaForm>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { useForm } from 'vuestic-ui'
import { useRouter } from 'vue-router'

const email = ref('')
const form = useForm('passwordForm')
const router = useRouter()

const submit = () => {
  if (form.validate()) {
    router.push({ name: 'recover-password-email' })
  }
}
</script>
