<template>
  <!--Form Section -->
  <section>
    <div class="container">
      <form @submit.prevent="createTweet" id="tweetForm" class="form">
        <input type="text" name="name" id="name" placeholder="Your name" class="name" >
        <input type="text" name="content" id="content" placeholder="Tweet here" class="tweet" >
        <button id="tweet" class="btn btn-primary">Tweet</button>
      </form>
    </div>
  </section>
  <!-- Tweet Table -->
  <section id="display">
    <div class="container">
      <table class="table table-success table-striped table-hover">
        <thead>
          <tr>
            <th>Date</th>
            <th>Tweet</th>
            <th>Name</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="tweet in tweets" :key="tweet.id">
            <td>{{tweet.created_at}}1</td>
            <td>{{tweet.content}}</td>
            <td>{{tweet.name}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
const baseURL = 'http://127.0.0.1:8000/tweet/' ;

export default {
  name: "display",
  data() {
    return {
      newTweet: {
        'Date': '',
        'Tweet': '',
        'Name': ''
      },
      tweets: []
    }
  },

  async created() {
    try {
      const response = await axios.get(baseURL);
      this.tweets = response.json();
    } catch(e) {
      return e
    }
  },
  // methods: {
  //   async createTweet() {
  //     const response = await axios.post(baseURL, {content: this.newTweet});

  //     this.tweets = [...this.tweets, response.data];
      
  //     this.newTweet = '';
  //   }
  // }
}

// const sendBtn = document.getElementById('tweet');

// sendBtn.addEventListener('click', (e) => {
//   e.preventDefault();

// })
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

  table {
    width: 100%;
    border: 1px solid gray;
  }
</style>