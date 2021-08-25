<template>
  <h4>Pricefy</h4>
  <input type="text" name="title" placeholder="What game are you searching? Ex. Minecraft" v-model="data.title" required>
  <br>
  <h3 v-show="data.title != ''" style="color: white">Click on the store that you want to check out ⬇</h3>
  <transition name="fade">
  <div v-show="data.title != ''" class="buttons">
    
    <BaseButton opts="50%" pathToImage='url("https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fdigitalmoneytimes.com%2Fwp-content%2Fuploads%2F2015%2F10%2FKinguin-Small-Transparent-300x300.png&f=1&nofb=1")' bgColor="white" :link="'https://www.kinguin.net/listing?phrase= '+ encodeURI(data.title) +'&active=0&sort=bestseller.total%2CDESC'" />
    <BaseButton opts="80%" pathToImage='url("https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2Fd%2Fda%2FLogo_g2a_icon.svg%2F800px-Logo_g2a_icon.svg.png&f=1&nofb=1")' bgColor="black" :link="'https://www.g2a.com/search?query='+ encodeURI(data.title)"/>
    <BaseButton opts="100%" pathToImage='url("https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.poulpeo.com%2Fupload%2Fmerchants_logo%2F200-120%2Finstant-gaming-T1591352635.png&f=1&nofb=1")' bgColor="orange" :link="'https://www.instant-gaming.com/en/search/?q='+ encodeURI(data.title)" />

  </div>
  </transition>
</template>

<script setup>
  import BaseButton from './components/BaseButton.vue';
  import { reactive } from 'vue';
  const data = reactive({ title: ''});


</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

body {
  background-color: #2c3e50;
  padding: 0;
  margin: 0;
  text-align: center;
}

h4 {
  text-align: center;
  font-weight: bold;
  font-size: 4rem;
  font-family: 'Pacifico';
  color: white;
  margin: 0.5em;
}

input {
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.11);
  border-radius: 4px;
  padding: 0.8em 0.8em;
  width: clamp(250px, 60%, 500px);
  position: relative;
}

.buttons {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 300ms;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.fade-enter-to, .fade-leave {
  opacity: 1;
}

</style>

