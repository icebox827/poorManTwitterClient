<template>
  <div class="container">
    <form action="" id="tweetForm" class="form">
      <input type="text" name="name" id="name" placeholder="Your name" class="name">
      <input type="text" name="inputTweet" id="inputTweet" placeholder="Tweet here" class="tweet">
      <input type="button" id="tweet" value="Tweet" class="btn">
    </form>
  </div>
</template>

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
</style>