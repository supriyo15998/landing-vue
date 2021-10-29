<template lang="">
  <div>
    <v-container>
      <v-row>
        <v-col cols="6">
          <v-card
            outlined
            max-width="70%"
            class="pa-3 mb-3 mt-3 mr-3 ml-3"
            @click.prevent="viewLoginButtonMethod()"
          >
            <v-row justify="center" class="mt-2 mb-2"><h3>Login</h3></v-row>
            <v-row>
              <v-text-field
                class="mr-3 ml-3 mt-1"
                label="Username"
                placeholder="Enter your username"
                outlined
                rounded
              ></v-text-field>
            </v-row>
            <v-row>
              <v-text-field
                type="password"
                class="mr-3 ml-3 mt-1"
                label="Password"
                placeholder="Enter the password"
                rounded
                outlined
              ></v-text-field>
            </v-row>
            <v-row justify="center" v-if="viewLoginButton">
              <v-btn
                class="mb-4 pa-3"
                rounded
                elevation="3"
                outlined
                color="primary"
                >Login</v-btn
              >
            </v-row>
          </v-card>
        </v-col>
        <v-col cols="6">
          <v-card
            outlined
            max-width="70%"
            class="pa-3 mb-3 mt-3 mr-3 ml-3"
            @click.prevent="viewRegisterButtonMethod()"
          >
            <v-row justify="center" class="mt-2 mb-2"><h3>Register</h3></v-row>
            <v-row>
              <v-text-field
                class="mr-3 ml-3 mt-1"
                label="Username"
                placeholder="Enter your username"
                outlined
                rounded
              ></v-text-field>
            </v-row>
            <v-row>
              <v-text-field
                type="password"
                class="mr-3 ml-3 mt-1"
                label="Password"
                placeholder="Enter the password"
                rounded
                outlined
              ></v-text-field>
            </v-row>
            <v-row justify="center" v-if="viewRegisterButton">
              <v-btn
                class="mb-4 pa-3"
                rounded
                elevation="3"
                outlined
                color="primary"
                >Register</v-btn
              >
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      viewLoginButton: false,
      viewRegisterButton: false
    };
  },
  methods: {
    viewLoginButtonMethod() {
      this.viewLoginButton = true;
    },
    viewRegisterButtonMethod() {
      this.viewRegisterButton = true;
    }
  }
};
</script>
<style lang=""></style>
