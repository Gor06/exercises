<template>
  <v-form>
    <v-container>
      <v-row>
        <v-col cols="12" sm="6">
          <v-text-field
            :append-icon="show3 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show3 ? 'text' : 'password'"
            name="input-10-2"
            label="Not visible"
            hint="At least 8 characters"
            value="wqfasds"
            class="input-group--focused"
            @click:append="show3 = !show3"
          ></v-text-field>
        </v-col>
        <v-col ols="12" sm="6">
          <v-text-field
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Normal with hint text"
            hint="At least 8 characters"
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
    name:'Login',
    data () {
      return {
        show1: false, 
        show2: true, 
        show3: false,
        show4: true,
        password: 'Password',
        rules: {
        required: value => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        semailMatch: () => ('The email and password you entered don\'t match'),
        },
      }
    },
}
</script>
