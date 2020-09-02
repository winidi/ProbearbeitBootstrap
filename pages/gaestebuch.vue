<template>
  <div class="container">
    <h1>Herzlich Willkommen! Tragen Sie sich gerne ein.</h1>
    <div class="col-xl">
      <label>
        <strong>Name:</strong>
      </label>
      <br />
      <input class="input" type="text" v-model="name" />
      <br />
      <label>
        <strong>Ihre Nachricht:</strong>
      </label>
      <br />
      <textarea type="text" v-model="text"></textarea>
      <br />
      <button class="sendbutton" v-on:click="addComment">Abschicken</button>
    </div>

    <hr />

    <div class="eintraege">
      <ul v-for="comment in usercomments" :key="comment.id">
        <hr />
        <strong>Name:</strong>
        <p class="pgast">{{comment.name}}</p>
        <strong>Nachricht:</strong>
        <br />
        {{comment.text}}
      </ul>
    </div>
  </div>
</template>


<script>
import axios from "axios";



export default {
  data() {
    return {
      name: "",
      text: "",
      usercomments: [],
    };
  },

  created(){
      this.loadData();
  },


  methods: {
    /// FUNKTIONIERT
    async addComment() {
      let newComment = {
        name: this.name,
        text: this.text,
      };
      console.log(this.name);
      const response = await axios
        .post("http://win.cim.local:3001/usercomments/", newComment)
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
      //reload
      window.location.reload(true);
    },

    async loadData() {
      const { data } = await axios.get(
        `http://win.cim.local:3001/usercomments`
      );
      console.log(data);
      this.usercomments = data;
    },
  },
};
</script>

<style scoped>
.eintraege {
  border: solid black;
}
.center-block {
  margin: auto;
}
.cincont {
  width: 50%;
  margin: 0 auto;
}
.guestbookbox {
  padding-left: 1em;
  width: 33em;
  margin: auto;
  border: 2px solid #ccc;
}
#msg {
  width: 33em;
  height: 16em;
}
</style>

<style scoped>
.col-xl {
  padding-top: 2em;
}

textarea {
  width: 44em;
  height: 12em;
}

.container {
  padding-top: 4em;
}
</style>