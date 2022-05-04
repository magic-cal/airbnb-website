<template>
  <v-theme-provider>
    <v-form ref="form" v-model="valid" lazy-validation>
      <div id="contact" />
      <v-text-field v-model="name" label="Name *" required></v-text-field>

      <v-text-field v-model="email" label="E-mail" validate-on-blur>
      </v-text-field>

      <v-text-field v-model="phone" label="Phone"></v-text-field>

      <v-menu
        v-model="datePopup"
        :close-on-content-click="false"
        transition="scale-transition"
        offset-y
        max-width="290px"
        min-width="auto"
      >
        <template #activator="{ on, attrs }">
          <v-text-field
            v-model="formattedDate"
            label="Start Date of Stay"
            prepend-icon="mdi-calendar"
            readonly
            v-bind="attrs"
            v-on="on"
          ></v-text-field>
        </template>
        <v-date-picker
          v-model="date"
          no-title
          @input="menu2 = false"
        ></v-date-picker>
      </v-menu>
      <v-textarea v-model="details" label="Event Details"> </v-textarea>

      <v-btn color="accent" class="mr-4" @click="sendEmail"> Send </v-btn>
    </v-form>
  </v-theme-provider>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from '@vue/composition-api'
import { send as emailSend } from 'emailjs-com'

export default defineComponent({
  name: 'Contact',
  setup() {
    const form = ref<any>(null)
    const name = ref('')
    const phone = ref('')
    const email = ref('')
    const date = ref('')
    const details = ref('')

    const valid = ref(true)
    const datePopup = ref(false)

    const formattedDate = computed(() => formatDate(date.value))

    const formatDate = (date: string) => {
      if (!date) return null

      const [year, month, day] = date.split('-')
      return `${day}-${month}-${year}`
    }

    const validate = () => {
      return form.value.validate()
    }

    const reset = () => {
      return form.value.reset()
    }
    const sendEmail = () => {
      if (!validate()) {
        return
      }
      emailSend(
        'service_j9477j5',
        'template_rs5lw1k',
        {
          name: name.value,
          phone: phone.value,
          email: email.value,
          date: formattedDate.value,
          details: details.value,
        },
        'user_B76eyVlaAaisRGhim1W5r'
      ).then(
        () => {
          console.log('SUCCESS!')
          alert('Sent')
          reset()
        },
        (error) => {
          console.log('FAILED...', error)
        }
      )
    }

    return {
      name,
      phone,
      email,
      date,
      valid,
      datePopup,
      formattedDate,
      details,
      sendEmail,
      form,
      validate,
      reset,
    }
  },
})
</script>
