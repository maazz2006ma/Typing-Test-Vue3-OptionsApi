<template>
  <div class="reactives">
    <span>
      <div>
        <span v-for="word in words" :key="word">{{ word.toUpperCase() }}</span>
      </div>
      <div class="user">
        <input
          :class="{ wrongAnswer: incorrectWord }"
          type="text"
          v-model="userEnteredWords"
          @input="checkWord"
          @keydown="handleBackspace($event)"
        />
      </div>
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      words: ["pillow ", "will ", "hello ", "police ", "likes "],
      userEnteredWords: "",
      incorrectWord: false,
      counter: 0,
      isCorrectWord: false,
      currentWord: 0
    };
  },
  methods: {
    checkWord() {
      if (
        this.words[this.counter].charAt(this.counter).toLocaleUpperCase() !==
        this.userEnteredWords.charAt(this.counter).toLocaleUpperCase()
      ) {
        this.counter++;
        this.incorrectWord = true;
      } else {
        this.counter++;
        this.incorrectWord = false;
      }
    },
    handleBackspace(event) {
      console.log("what is wrong here")
      if (event.keyCode === 8 && this.counter !== 0) this.counter--;
    },
  },
  computed:{
   
  },  
  watch: {
    userEnteredWords(newVal) {
      this.userEnteredWords = newVal.toUpperCase();
    },
  },
};
</script>
<style scoped>
.reactives {
  display: flex;
  justify-content: center;
}
div {
  margin-bottom: 15px;
}
.user {
  border: none;
  background-color: antiquewhite;
  width: 500px;
  height: 250px;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
}
span {
  font-size: xx-large;
}
input {
  width: 80%;
  height: 20%;
  border-radius: 15px;
  padding-left: 50px;
  line-height: 25px;
  font-size: 25px;
}
.wrongAnswer {
  text-decoration: line-through;
}
</style>
