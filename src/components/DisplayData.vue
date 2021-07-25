<template>
  <div>
    <h1>Displaying Posts...</h1>
    <div v-if="!dataFetchComplete" class="loader" id="loader">
        <img src="../assets/loader.svg" alt="Loading">
    </div>
    <ul v-else>
      <li v-for="(data, index) in posts" :key="index">
      <h2 id="heading">{{ data.title }}</h2>
      <p><b>UserId:</b> {{ data.userId }}</p>
      <p><b>Id:</b> {{ data.id }}</p>
      <p>{{ data.body }}</p>
    </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      posts: [],
      apiUrl: 'https://jsonplaceholder.typicode.com/posts',
      dataFetchComplete: false,
    }
  },
  async mounted() {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    this.posts = await response.json();
    if (this.posts.length) {
      this.dataFetchComplete = true;
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Zen+Tokyo+Zoo&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Baloo+Chettan+2&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Alfa+Slab+One&display=swap');
  p {
    text-align: justify;
    margin-left: 2%;
    font-family: 'Baloo Chettan 2', sans-serif;
    color: black;
  }
  h1 {
    font-family: 'Zen Tokyo Zoo', sans-serif;
    letter-spacing: 3px;
    font-size: 50px;
  }
  #heading {
    font-family: 'Alfa Slab One', sans-serif;
    font-size: 20px;
    letter-spacing: 2px;
  } 
  li {
    list-style: auto;
  }
  .loader {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.8);
}
.loader img {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>