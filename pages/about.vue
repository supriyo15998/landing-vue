<template>
  <div>
    <v-row class="mt-3 mb-3" justify="center">
      <h1>{{ name }}</h1>
    </v-row>

    <v-card outlined class="pa-3 mb-3 mt-3">
      <v-card>
        <v-row justify="center" class="mt-2">
          <h3>Contributors</h3>
        </v-row>
        <v-row>
          <v-col
            cols="3"
            v-for="contributor in contributors"
            :key="contributor.id"
          >
            <v-card
              outlined
              @click.prevent="getContributorGithubProfile(contributor.githubId)"
            >
              <v-card-title>
                <v-icon large>mdi-account-circle</v-icon>
                {{ contributor.firstName }}
              </v-card-title>
            </v-card>
          </v-col>
        </v-row>
        <v-row v-if="resultFetch">
          <v-col cols="12">
            <v-card> <v-card-title>test</v-card-title> </v-card>
          </v-col>
        </v-row>
      </v-card>
    </v-card>
  </div>
</template>
<script>
import * as axios from "axios";

const API = "https://api.github.com/users/";
export default {
  data() {
    return {
      name: "Hello Hacktober fest 2021",
      resultFetch: false,
      contributors: [
        {
          id: 1,
          firstName: "Supriyo",
          lastName: "Das",
          githubId: "supriyo15998"
        },
        {
          id: 2,
          firstName: "Faraz",
          lastName: "Ali",
          githubId: "farazappy"
        },
        {
          id: 3,
          firstName: "Anikesh",
          lastName: "Sinha",
          githubId: "AnikS0498"
        },
        {
          id: 4,
          firstName: "Sameema",
          lastName: "Nasrin",
          githubId: "SameemaNasrin"
        }
      ]
    };
  },

  methods: {
    async getContributorGithubProfile(githubId) {
      let response = await axios.get(API + githubId);
      if (response.status == 200) {
        console.log(response.data);
        console.log(this.githubId);
        this.resultFetch = true;
      }
    }
  }
};
</script>
<style lang=""></style>
