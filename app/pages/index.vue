<script setup>
import { ref, onMounted } from "vue"

const temperature = ref(null)
const windspeed = ref(null)

const getWeather = async () => {
  const response = await fetch(
    "https://api.open-meteo.com/v1/forecast?latitude=-25.7461&longitude=28.1881&current_weather=true"
  )

  const data = await response.json()

  temperature.value = data.current_weather.temperature
  windspeed.value = data.current_weather.windspeed
}

onMounted(() => {
  getWeather()
})
</script>


<template>
    <h1>ABOUT ME</h1>
    <img src="/profile.jpg" alt="My Photo" class="profile-img">
    <h2>Hello! I'm Junior Ntsika Tshuma</h2>
    <h3>Mulitimedia student</h3>
    <p>
         I'm, a multimedia student at the University of Pretoria, passionate about combining creativity and technology.
         I'm currently working towards my goal of becoming a full-stack developer, building skills in both front-end and back-end 
         development. I value innovation, collaboration, and practical problem-solving in every project I tackle. Beyond coding,
         I enjoy exploring digital design, multimedia projects, and staying updated on tech trends.Some of the hobbies i get up
         to are playing basketball, football and lots of late night gaming. I'm always eager to connect with fellow developers,
         creatives, and anyone interested in building impactful digital experiences let's collaborate and bring ideas to life!
    </p>

         <h2>Current Weather in Pretoria</h2>

    <p v-if="temperature !== null">
      🌡️ Temperature: {{ temperature }} °C
    </p>

    <p v-if="windspeed !== null">
      💨 Wind Speed: {{ windspeed }} km/h
    </p>

    <footer>
    <p>Ntsika Tshuma &copy; 2026</p>
  </footer>

</template>

<style>
.profile-img{
  width:400px;
  border-radius:50%;
  margin:20px 0;
  border:4px solid #e6c7a8;
}

p{
  max-width:700px;
  margin:auto;
  line-height:1.6;
}

/* Main container */
.container{
  text-align: center;
  padding: 30px;
}


</style>