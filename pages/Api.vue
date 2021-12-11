<template>
  <div class="container">
     <div class="row">
        <!-- Create row with title and two p of text -->
        <div class="col mt-3">
            <h1 class="m-3" >Schedule your appointment today!</h1>
            <div class="row box-1 bg-light m-3" v-for="msg in text" v-bind:key="msg">
            </div>
            <h2 class="m-3">Seattle </h2>
              <p> Test </p>
            <h2 class="m-3">Yakima </h2>
              <p> Test </p>
        </div>
      </div>
  </div>
</template>

<script>

 export default {
    data() {
      return {
        //  Seattle site
        weatherOne: [],
        // Yakima site
        weatherTwo: []
      }
    },
    async fetch() {
      this.weatherOne = await fetch(
        'https://api.weather.gov/gridpoints/SEW/125,50/forecast'
      ).then(res => res.json()),
      this.weatherTwo = await fetch(
        'https://api.weather.gov/gridpoints/PDT/88,139/forecast'
      ).then(res => res.json())
    }
  }


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

@import "../scss/_base.normalize.scss";
@import "../scss/_components.content.scss";
@import "../scss/_settings.responsive.scss";
@import "../scss/_settings.variables.scss";
@import "../scss/style.scss";


</style>
