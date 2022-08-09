<template>
  <header>
    <div class="fContainer sticky">
      <nav class="wrapper">
        <div class="brand">
          <div class="firstname">yo</div>
          <div class="lastname">dang</div>
        </div>
        <ul class="navigation">
          <li><a href="#about">about</a></li>
          <li><a href="#portfolio" class="active">portfolio</a></li>
          <li><a href="#contact">contact</a></li>
          <li><img src="/img/mentally.gif" alt="gif" /></li>
        </ul>
      </nav>
    </div>
    <!-- menu mobile -->
    <label for="check" class="mobile-menu"><i class="fas fa-bars fa-2x"></i></label>
    <!-- bagian jumbotron -->
    <div class="jumbotron">
      <div class="jumbotron-left">
        <img src="/img/profilepic.jpg" />
        <h2>
          Hello, I&#39;m Yohanes<br />
          I&#39;m a <span ref="berjalan"></span>
        </h2>
        <p>
          With a Strong Analytical Skills, Strategic Thinking,Creativity, <br />Good
          Communication and Negotiation.
        </p>
      </div>
    </div>
  </header>
</template>

<script setup lang="ts">
import { onMounted, ref } from "vue";

const txtElement = ["Student", "Programmer", "Gamer"];
let count = 0;
let txtIndex = 0;
let currentTxt = "";
let words = "";

onMounted(() => {
  typingefect();
});
const berjalan = ref();

function typingefect() {
  if (count == txtElement.length) {
    count = 0;
  }

  currentTxt = txtElement[count];

  words = currentTxt.slice(0, ++txtIndex);
  if (berjalan != undefined) {
    berjalan.value.textContent = words;
  }

  if (words.length == currentTxt.length) {
    count++;
    txtIndex = 0;
  }

  setTimeout(typingefect, 500);
}
</script>

<style scoped>
.sticky {
  position: fixed;
  top: 0;
  left: auto;
  z-index: 10;

}
</style>