<template>
  <div class="container">
     <b-row>
    <b-col md="auto">
      <b-calendar v-model="value" @context="onContext" locale="en-US"></b-calendar>
    </b-col>
    <b-col>
      <p>Value: <b>'{{ value }}'</b></p>
      <p class="mb-0">Context:</p>
      <pre class="small">{{ context }}</pre>
    </b-col>
  </b-row>
  </div>
</template>

<script>

 export default {
    data() {
      return {
        //  Seattle site
        weatherOne: [],
        // Yakima site
        weatherTwo: [],
        value: '',
        context: null
      }
    },
     methods: {
      onContext(ctx) {
        this.context = ctx
      }
    },
    async fetch() {
      // this.weatherOne = await fetch(
      //   'https://api.weather.gov/gridpoints/SEW/125,50/forecast'
      // ).then(res => res.json()),
      // this.weatherTwo = await fetch(
      //   'https://api.weather.gov/gridpoints/PDT/88,139/forecast'
      // ).then(res => res.json())
    }
  }

  let a = {
    "@context": [
        "https://geojson.org/geojson-ld/geojson-context.jsonld",
        {
            "@version": "1.1",
            "wx": "https://api.weather.gov/ontology#",
            "geo": "http://www.opengis.net/ont/geosparql#",
            "unit": "http://codes.wmo.int/common/unit/",
            "@vocab": "https://api.weather.gov/ontology#"
        }
    ],
    "type": "Feature",
    "geometry": {
        "type": "Polygon",
        "coordinates": [
            [
                [
                    -122.20252189999999,
                    47.270626999999998
                ],
                [
                    -122.1963473,
                    47.250020899999996
                ],
                [
                    -122.16603050000001,
                    47.254202899999996
                ],
                [
                    -122.17219850000001,
                    47.274809199999993
                ],
                [
                    -122.20252189999999,
                    47.270626999999998
                ]
            ]
        ]
    },
    "properties": {
        "updated": "2021-12-11T17:55:59+00:00",
        "units": "us",
        "forecastGenerator": "BaselineForecastGenerator",
        "generatedAt": "2021-12-11T19:44:09+00:00",
        "updateTime": "2021-12-11T17:55:59+00:00",
        "validTimes": "2021-12-11T11:00:00+00:00/P7DT14H",
        "elevation": {
            "unitCode": "wmoUnit:m",
            "value": 149.0472
        },
        "periods": [
            {
                "number": 1,
                "name": "Today",
                "startTime": "2021-12-11T11:00:00-08:00",
                "endTime": "2021-12-11T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 46,
                "temperatureUnit": "F",
                "temperatureTrend": "falling",
                "windSpeed": "8 to 16 mph",
                "windDirection": "SW",
                "icon": "https://api.weather.gov/icons/land/day/rain,90?size=medium",
                "shortForecast": "Light Rain",
                "detailedForecast": "Rain before 4pm, then rain showers. Cloudy. High near 46, with temperatures falling to around 41 in the afternoon. Southwest wind 8 to 16 mph, with gusts as high as 21 mph. Chance of precipitation is 90%. New rainfall amounts between a tenth and quarter of an inch possible."
            },
            {
                "number": 2,
                "name": "Tonight",
                "startTime": "2021-12-11T18:00:00-08:00",
                "endTime": "2021-12-12T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 35,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "7 to 12 mph",
                "windDirection": "SSW",
                "icon": "https://api.weather.gov/icons/land/night/rain_showers,90/snow,100?size=medium",
                "shortForecast": "Rain Showers then Rain And Snow Showers",
                "detailedForecast": "Rain showers before 4am, then rain and snow showers. Cloudy, with a low around 35. South southwest wind 7 to 12 mph. Chance of precipitation is 100%. New rainfall amounts between a quarter and half of an inch possible."
            },
            {
                "number": 3,
                "name": "Sunday",
                "startTime": "2021-12-12T06:00:00-08:00",
                "endTime": "2021-12-12T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 42,
                "temperatureUnit": "F",
                "temperatureTrend": "falling",
                "windSpeed": "10 mph",
                "windDirection": "S",
                "icon": "https://api.weather.gov/icons/land/day/snow,100?size=medium",
                "shortForecast": "Rain And Snow Showers",
                "detailedForecast": "Rain and snow showers. Cloudy. High near 42, with temperatures falling to around 39 in the afternoon. South wind around 10 mph. Chance of precipitation is 100%. New rainfall amounts between a tenth and quarter of an inch possible."
            },
            {
                "number": 4,
                "name": "Sunday Night",
                "startTime": "2021-12-12T18:00:00-08:00",
                "endTime": "2021-12-13T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 34,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "3 to 8 mph",
                "windDirection": "ESE",
                "icon": "https://api.weather.gov/icons/land/night/rain_showers,90/rain,80?size=medium",
                "shortForecast": "Rain Showers then Light Rain",
                "detailedForecast": "Rain showers before 4am, then rain. Cloudy, with a low around 34. East southeast wind 3 to 8 mph. Chance of precipitation is 90%. New rainfall amounts less than a tenth of an inch possible."
            },
            {
                "number": 5,
                "name": "Monday",
                "startTime": "2021-12-13T06:00:00-08:00",
                "endTime": "2021-12-13T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 42,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "3 mph",
                "windDirection": "SE",
                "icon": "https://api.weather.gov/icons/land/day/snow,80?size=medium",
                "shortForecast": "Rain And Snow",
                "detailedForecast": "Rain before 7am, then rain and snow. Mostly cloudy, with a high near 42. Southeast wind around 3 mph. Chance of precipitation is 80%. New rainfall amounts less than a tenth of an inch possible."
            },
            {
                "number": 6,
                "name": "Monday Night",
                "startTime": "2021-12-13T18:00:00-08:00",
                "endTime": "2021-12-14T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 32,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "3 mph",
                "windDirection": "SSE",
                "icon": "https://api.weather.gov/icons/land/night/snow,70/snow,50?size=medium",
                "shortForecast": "Chance Rain And Snow",
                "detailedForecast": "Rain likely before 10pm, then a chance of rain and snow. Mostly cloudy, with a low around 32. Chance of precipitation is 70%. Little or no snow accumulation expected."
            },
            {
                "number": 7,
                "name": "Tuesday",
                "startTime": "2021-12-14T06:00:00-08:00",
                "endTime": "2021-12-14T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 41,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "5 mph",
                "windDirection": "S",
                "icon": "https://api.weather.gov/icons/land/day/snow,40/snow,50?size=medium",
                "shortForecast": "Chance Rain And Snow",
                "detailedForecast": "A chance of rain and snow. Mostly cloudy, with a high near 41. Chance of precipitation is 50%. Little or no snow accumulation expected."
            },
            {
                "number": 8,
                "name": "Tuesday Night",
                "startTime": "2021-12-14T18:00:00-08:00",
                "endTime": "2021-12-15T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 31,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "5 mph",
                "windDirection": "SSE",
                "icon": "https://api.weather.gov/icons/land/night/snow?size=medium",
                "shortForecast": "Rain And Snow Likely",
                "detailedForecast": "Rain and snow likely. Mostly cloudy, with a low around 31. Little or no snow accumulation expected."
            },
            {
                "number": 9,
                "name": "Wednesday",
                "startTime": "2021-12-15T06:00:00-08:00",
                "endTime": "2021-12-15T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 41,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "5 mph",
                "windDirection": "E",
                "icon": "https://api.weather.gov/icons/land/day/snow?size=medium",
                "shortForecast": "Light Snow Likely",
                "detailedForecast": "Snow likely before 10am, then rain and snow likely. Mostly cloudy, with a high near 41. Little or no snow accumulation expected."
            },
            {
                "number": 10,
                "name": "Wednesday Night",
                "startTime": "2021-12-15T18:00:00-08:00",
                "endTime": "2021-12-16T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 31,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "5 mph",
                "windDirection": "ESE",
                "icon": "https://api.weather.gov/icons/land/night/snow?size=medium",
                "shortForecast": "Rain And Snow Likely",
                "detailedForecast": "Rain likely before 7pm, then rain and snow likely. Mostly cloudy, with a low around 31."
            },
            {
                "number": 11,
                "name": "Thursday",
                "startTime": "2021-12-16T06:00:00-08:00",
                "endTime": "2021-12-16T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 41,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "3 mph",
                "windDirection": "S",
                "icon": "https://api.weather.gov/icons/land/day/snow?size=medium",
                "shortForecast": "Chance Rain And Snow",
                "detailedForecast": "A chance of rain and snow. Partly sunny, with a high near 41."
            },
            {
                "number": 12,
                "name": "Thursday Night",
                "startTime": "2021-12-16T18:00:00-08:00",
                "endTime": "2021-12-17T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 31,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "3 mph",
                "windDirection": "SSE",
                "icon": "https://api.weather.gov/icons/land/night/snow?size=medium",
                "shortForecast": "Chance Rain And Snow",
                "detailedForecast": "A chance of rain and snow. Mostly cloudy, with a low around 31."
            },
            {
                "number": 13,
                "name": "Friday",
                "startTime": "2021-12-17T06:00:00-08:00",
                "endTime": "2021-12-17T18:00:00-08:00",
                "isDaytime": true,
                "temperature": 41,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "3 mph",
                "windDirection": "SSE",
                "icon": "https://api.weather.gov/icons/land/day/snow?size=medium",
                "shortForecast": "Rain And Snow Likely",
                "detailedForecast": "Rain and snow likely. Partly sunny, with a high near 41."
            },
            {
                "number": 14,
                "name": "Friday Night",
                "startTime": "2021-12-17T18:00:00-08:00",
                "endTime": "2021-12-18T06:00:00-08:00",
                "isDaytime": false,
                "temperature": 34,
                "temperatureUnit": "F",
                "temperatureTrend": null,
                "windSpeed": "2 to 6 mph",
                "windDirection": "S",
                "icon": "https://api.weather.gov/icons/land/night/snow?size=medium",
                "shortForecast": "Rain And Snow Likely",
                "detailedForecast": "Rain likely before 7pm, then rain and snow likely. Mostly cloudy, with a low around 34."
            }
        ]
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
