<template>
  <div class="myCLubs">
    <h1 class="d-flex justify-center mt-6">My Clubs</h1>

    <v-container class="px-10">

      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="club in myClubs" :key="club.name">
          <v-card  class="text-center ma-3 pt-3">
            <v-card-text>
              <h2>{{ club.name }}</h2>
            </v-card-text>

            <v-responsive class="pt-4">
              <v-img :aspect-ratio="14/9"  :src="club.picture"></v-img>
            </v-responsive>

            <v-card-actions :to="club.route">
              <v-spacer></v-spacer>
              <v-btn flat depressed color="white grey--text" :to="club.route">
                <span>Explore</span>
                <v-icon small right>mdi-arrow-right</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>

    </v-container>

  </div>
</template>

<script>
export default {
  name: 'MyClubs',
  data() {
    return {
      myClubs: [
        { name: 'Model UN', picture: require('../../images/munGroup.jpg'), route: '/modelun' },
        { name: 'Math Team', picture: require('../../images/mtGroup.jpeg'), route: '/mathteam' },
        { name: 'NTHS', picture: require('../../images/nths.jpg'), route: '/nths' },
        { name: 'AOE', picture: require('../../images/aoeGroup.jpeg'), route: '' },
      ]
    }
  }
}
</script>