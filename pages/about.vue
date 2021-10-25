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
            <v-card outlined @click.prevent="getContributorGithubProfile()">
              <v-card-title>
                <v-icon large>mdi-account-circle</v-icon>
                {{ contributor.firstName }}
              </v-card-title>
            </v-card>
            <v-row v-if="resultFetch" class="mt-2">
              <v-col>
                <v-card outlined>
                  <v-card-title>
                    <a :href="contributor.githubProfileUrl" target="_blank">
                      Github Profile
                    </a>
                  </v-card-title>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-card>
    </v-card>
  </div>
</template>
<script>
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
          githubProfileUrl: "https://github.com/supriyo15998"
        },
        {
          id: 2,
          firstName: "Faraz",
          lastName: "Ali",
          githubProfileUrl: "https://github.com/farazappy"
        },
        {
          id: 3,
          firstName: "Anikesh",
          lastName: "Sinha",
          githubProfileUrl: "https://github.com/AnikS0498"
        },
        {
          id: 4,
          firstName: "Sameema",
          lastName: "Nasrin",
          githubProfileUrl: "https://github.com/SameemaNasrin"
        }
      ]
    };
  },

  methods: {
    getContributorGithubProfile() {
      this.resultFetch = !this.resultFetch;
    }
  }
};
</script>
<style lang=""></style>
