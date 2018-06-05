<template>
  <v-app>
    <v-container grid-list-xl text-xs-center>
      <v-layout row wrap>
        <v-flex xs10 offset-xs1>
          <v-card color="white" class="pa-5">
            <v-form ref="form" lazy-validation>
              <v-text-field
                :counter="10"
                label="Name"
                required>
              </v-text-field>
              <v-text-field
                label="E-mail"
                required>
              </v-text-field>

              <v-btn color="success">submit</v-btn>
            </v-form>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script></script>

<style scoped>

</style>
