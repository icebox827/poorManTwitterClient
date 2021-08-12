<template>
  <!--Form Section -->
  <section>
    <div class="container">
      <form action="" id="tweetForm" class="form">
        <input type="text" name="name" id="name" placeholder="Your name" class="name">
        <input type="text" name="inputTweet" id="inputTweet" placeholder="Tweet here" class="tweet">
        <input type="button" id="tweet" value="Tweet" class="btn">
      </form>
    </div>
  </section>
  <!-- Tweet Table -->
  <section id="display">
    <div class="container">
      <table>
        <tr>
          <th>Date</th>
          <th>Tweet</th>
          <th>name</th>
        </tr>
        <tr>
          <td v-for="tweet of tweets" :key="tweet.id">{{tweet.create_at}}</td>
          <td v-for="tweet of tweets" :key="tweet.id">{{tweet.content}}</td>
          <td v-for="tweet of tweets" :key="tweet.id">{{tweet.name}}</td>
        </tr>
      </table>
    </div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
  name: "display",
  data() {
    return {
      tweets: []
    }
  },

  async created() {
    try {
      const response = await axios.get(`http://127.0.0.1:8000/tweet/`);

      this.tweets = response.data
    } catch(e) {
      return e
    }
  }
}

const sendBtn = document.getElementById('tweet');

sendBtn.addEventListener('click', (e) => {
  e.preventDefault();

})
</script>

<style>
  .container {
    display: flex;
    justify-content: center;
    margin-top: 60px;
  }

  .form input {
    margin: 10px;
    border-radius: 5px;
  }

  .form .tweet {
    width: 60vh;
  }

  .form .btn {
    background-color: rgb(61, 61, 250);
    color: white;
  }

  table {
    width: 70%;
    border: 1px solid gray;
  }
</style>