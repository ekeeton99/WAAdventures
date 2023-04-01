<template>
    <div class="main-content">
        <h1>Weather</h1>
        <card
            v-for="(forecast, key, index) in forecasts"
            :key="key"
            :time="forecasts['time'][index]"
            :high="forecasts['temperature_2m_max'][index]"
            :low="forecasts['temperature_2m_min'][index]"
            :uv="forecasts['uv_index_max'][index]"
        />
    </div>
</template>

<script>
import axios from "axios";
import card from "../components/card.vue"

export default {
    components: {
        card
    },
    data() {
        return {
            loading: true,
            weather: null,
            errored: false,
            forecasts: []
        }
    },
    mounted() {
        axios
            .get('https://api.open-meteo.com/v1/forecast?latitude=47.61&longitude=-122.33&hourly=temperature_2m,precipitation_probability,precipitation,windspeed_10m,winddirection_10m&daily=temperature_2m_max,temperature_2m_min,uv_index_max&temperature_unit=fahrenheit&windspeed_unit=mph&precipitation_unit=inch&timezone=America%2FLos_Angeles')
            .then(response => {
                (this.forecasts = response.data.daily);
                console.log(response.data.daily);
            })
            .catch(error => {
                console.log(error)
            })
            .finally(() => this.loading = false)
    }
}
</script>

<style>

</style>