<!-- TEMPLATE -->
<template>
  <div>
    <header class="sentences">
      <h3 v-if="moodValue <= 50">{{ a1 }}</h3>
      <h3 v-else-if="moodValue > 50 && moodValue <= 100">{{ a2 }}</h3>
      <h3 v-else-if="moodValue > 100 && moodValue <= 150">{{ a3 }}</h3>
      <h3 v-else-if="moodValue > 150 && moodValue <= 200">{{ a4 }}</h3>
      <h3 v-else-if="moodValue > 200 && moodValue <= 250">{{ a5 }}</h3>
      <h3 v-else-if="moodValue > 250 && moodValue <= 300">{{ a6 }}</h3>
    </header>

    <p class="intro">{{ intro }}</p>
    
    <section>
      <article class="movie-container">
        <div>
          <img class="movie-poster" :src="result.poster" alt="Movie poster">
        </div>
        <div>
          <h4 class="movie-title">{{ result.title }}</h4>
          <p class="movie-year">{{ result.year }}</p>
          <p> {{ result.description }}</p>
          <div class="movie-genres">
            <p v-for="genre in result.genres" :key="genre">{{ genre }}</p>
          </div>
        </div>
      </article>
    </section>

    <button class="main-btn back-btn" @click="goBack">Change the mood</button>
  </div>
</template>

<!-- SCRIPT -->
<script type="text/javascript" src="@/scripts/recommendation.js"></script>

<!-- STYLE -->
<style src="@/styles/css/recommendation.css"></style>