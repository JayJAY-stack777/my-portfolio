<script setup>
import { ref, onMounted } from "vue"

const anime = ref(null)

const getAnime = async () => {
  const response = await fetch("https://api.jikan.moe/v4/anime/20")
  const data = await response.json()
  anime.value = data.data
}

onMounted(() => {
  getAnime()
})
</script>

<template>
  
    <h1>My Projects</h1>
    <br>
    <br>
    <ul>
      <li><h3>God of War Website</h3>
        <p>
            A web application information on the God of War Ragnarok
            <a href="/files/God of War Website.zip" target="_blank">
            View / Download Project
            </a>
        </p>
      </li>
      <br>
       <br>
      <li> <h3>Comic book</h3>
  <p>
              A comic about a scientist and dinosaurs 
              <a href="/files/Comic Book.pdf" target="_blank">
              View / Download Project
              </a>
          </p>  
      </li>
      <br>
       <br>
      <li> <h3>Mulitimedia Project day poster</h3>
          <p>
              A poster created for multimedia project day.
              <a href="/files/Project Day Poster.zip" target="_blank">
              View / Download Project
              </a>
          </p>  
      </li>
    </ul>

         <h1>Featured Anime</h1>

    <div v-if="anime">

      <h2>{{ anime.title }}</h2>

      <img :src="anime.images.jpg.image_url" width="250">

      <p><strong>⭐ Rating:</strong> {{ anime.score }}</p>

      <p><strong>📺 Episodes:</strong> {{ anime.episodes }}</p>

      <p><strong>Synopsis:</strong></p>
      <p>{{ anime.synopsis }}</p>

    </div>

    <footer>
    <p>Ntsika Tshuma &copy; 2026</p>
  </footer>
  
</template>