<template>
  <div class="top">
    <b-img class="top-image" src="https://cdn.pixabay.com/photo/2016/12/22/22/07/hands-1926414_1280.jpg" fluid alt="Responsive image"></b-img>

    <router-link to="/posts">
      <b-button variant="outline-dark">
        <p>Pray For The World ></p>
      </b-button>
    </router-link>
  </div>
</template>

<style scoped>
div {
  height: 800px;
}
.top-image {
  margin-top: 20px;
  width: 85%;
  height: 70%;
  }
.top {
  background-color: white;
}

button {
  width: 60%;
  margin-top: 50px;
  border-radius: 3em;
  background-color: white;
}

button:hover {
  background-color: rgb(221, 221, 221);
}

.top p {
  padding: 10px 0 0 0;
  font-size: 30px;
  color: #888888;
}
</style>
