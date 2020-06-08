<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    Hi Christian
    {{greet}}
    <br>
    <input v-model="song">
    <button @click="myList.push(song)">Add audio url</button>
    <ol>
      <li v-for="item in myList">
        {{item}}
        <button @click="play(item)">Play</button>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function() {
    return {
      greet: "Welcome",
      song: "http://soundbible.com/mp3/Yess-Fabio_Farinelli-187689388.mp3",
      myList: [
        "http://soundbible.com/mp3/chinese-gong-daniel_simon.mp3",
        "http://soundbible.com/mp3/glass_ping-Go445-1207030150.mp3"
      ]
    };
  },
  methods: {
    play(audioUrl) {
      let audio = new Audio();
      audio.src = audioUrl;
      audio.play();
    }
  }
};
</script>
