<template>
  <v-container>
    <!-- <v-layout> -->

    <h1 class="display-1 text-xs-center">Weather App</h1>
    <v-flex xs12>
      <v-card dark>
        <v-card-text>Hello world {{ this.name }}</v-card-text>
      </v-card>
    </v-flex>
    <v-form @submit.prevent="getWeatherInfo">
      <v-text-field label="Enter City name" v-model="city"></v-text-field>
    </v-form>
    <!-- </v-layout> -->
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      city: "London",
      name:'',
      result:{

      }
    };
  },
  created() {
    
  },
  methods: {
      getWeatherInfo() {
this.$axios
      .$get(
        `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${process.env.weatherAppId}
`
      )
      .then((res) => {
          this.result=res
      });
      }
      
  }
};
</script>