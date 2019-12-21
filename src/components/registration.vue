<template>
  <v-form>
    <v-container>
      <v-row>

        <v-col cols="12" sm="6">
          <v-text-field
            v-model="first"
            label="First Name"
            :rules="[rules.required, rules.minn]"
            hint="At least 3 characters"
            name="input-10-1"
            filled
            counter
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            v-model="last"
            label="Last Name"
            :rules="[rules.required, rules.minn]"
            hint="At least 3 characters"
            filled
            counter
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="last"
            :rules="[rules.required, rules.min]"
            hint="At least 8 characters"
            label="Email"
            filled
            counter
          ></v-text-field>
        </v-col>
        <v-col ols="12" sm="6">
          <v-text-field
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Password"
            hint="At least 8 characters"
            filled
            counter
            @click:append="show1 = !show1"
          ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
  </v-form> 
  </template>
<script>
  export default {
    name:'Registration',
      first: 'John',
      last: 'Doe',
    data () {
      return {
        show1: false, 
        show2: true, 
        show3: false,
        show4: true,
        password: null,
        rules: {
        required: value                                                               => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        minn: v => v.length >= 2|| 'Min 8 characters',
        semailMatch: () => ('The email and password you entered don\'t match'),
        },
      }
    },
}
</script>
