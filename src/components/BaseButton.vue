<template>
  <a
    :style="{ 'background-color': bgColor, 'background-size': (opts ? opts : 'contain') , 'background-image': pathToImage }"
    class="button"
    :href="link.trim()"
    target="_blank"
  ></a>
</template>

<script>
export default {
  name: 'BaseButton',
  props: ["link", "bgColor", "pathToImage", "opts"]
};
</script>

<style scoped>
.button {
  padding: 4em 7em;
  border-radius: 5px;
  margin: 1em;
  text-decoration: none;
  color: white;

  background-size: contain;
  background-position: center center;
  background-repeat: no-repeat;
}
</style>