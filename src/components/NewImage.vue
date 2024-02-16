<template>
  <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg">
    <p class="text-h3 font-italic">
      Streamline Vulnerability Discovery, Prioritization, and Remediation for
      Applications & APIs into a Single, Automated Solution..
    </p>
    <v-row   justify="center">
      <v-col cols="14" sm="6" md="4">
        <v-dialog width="1000">
          <template v-slot:activator="{ props }">
            <v-btn
              v-bind="props"
              text="Request Demo"
              height="52"
              min-width="164"
              variant="outlined"
              rounded="xl"
              size="small"
              elevation="10"

            >
            </v-btn>
            <p class="text-h6">Click On Request Demo to Get The Form</p>

            
          </template>

          <template v-slot:default="{ isActive }">
            <v-card title="Form">
              <MyForm></MyForm>
              <v-card-actions>
                <v-spacer></v-spacer>

              

                <v-col cols="15" sm="4" md="3">
                  <v-btn
                    @click="isActive.value = false"
                    height="52"
                    min-width="164"
                    variant="outlined"
                    block rounded="xl"
                    size="small"
                    elevation="10"
                    >Close</v-btn
                  >
                </v-col>
              </v-card-actions>
            </v-card>
          </template>
        </v-dialog>
      </v-col>
    </v-row>
  </v-parallax>
</template>

<script>
import MyForm from "./MyForm.vue";

export default {
  name: "NewImage",
  data: () => ({}),
  components: { MyForm },
};
</script>
