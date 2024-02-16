<template>
  <form @submit.prevent="submit">
    <v-col cols="12" md="2">
      <v-select
        variant="underlined"
        v-model="select.value.value"
        :items="items"
        :error-messages="select.errorMessage.value"
        label="Select*"
      ></v-select
    ></v-col>

    <v-col cols="12" md="12">
      <v-text-field
        variant="underlined"
        v-model="name.value.value"
        :counter="10"
        :error-messages="name.errorMessage.value"
        label="Name*"
      ></v-text-field
    ></v-col>

    <v-col cols="12" md="12">
      <v-text-field
        variant="underlined"
        v-model="phone.value.value"
        :counter="10"
        :error-messages="phone.errorMessage.value"
        label="Phone Number*"
      ></v-text-field
    ></v-col>

    <v-col cols="12" md="12">
      <v-text-field
        variant="underlined"
        v-model="email.value.value"
        :error-messages="email.errorMessage.value"
        label="E-mail*"
      ></v-text-field
    ></v-col>

    <v-container>
      <v-row>
        <v-btn
          elevation="10"
          rounded="lg"
          variant="outlined"
          class="me-4"
          type="submit"
        >
          submit
        </v-btn>

        <v-btn
          elevation="10"
          variant="outlined"
          rounded="lg"
          @click="handleReset"
        >
          clear
        </v-btn>
      </v-row>
    </v-container>
    <p class="text-h6 font-italic text--red">*Indicates Required Fields</p>
  </form>
</template>
<script setup>
import { ref } from "vue";
import { useField, useForm } from "vee-validate";

const { handleSubmit, handleReset } = useForm({
  validationSchema: {
    name(value) {
      if (value?.length >= 3) return true;

      return "Name needs to be at least 3 characters.";
    },
    phone(value) {
      if (value?.length > 10 && /[0-10-]+/.test(value)) return true;

      return "Phone number needs to be at least 10 digits.";
    },
    email(value) {
      if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true;

      return "Must be a valid e-mail.";
    },
    select(value) {
      if (value) return true;

      return "Select an item.";
    },
  },
});
const name = useField("name");
const phone = useField("phone");
const email = useField("email");
const select = useField("select");

const items = ref(["Male", "Female", "Others"]);

const submit = handleSubmit((values) => {
  alert(JSON.stringify(values, null, 2));
});
</script>
