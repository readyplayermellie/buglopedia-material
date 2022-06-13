<template>
  <div id="welcome-text">
    <h2>{{ title }}</h2>
    <p>{{ text }}</p>
  </div>
</template>

<script setup>
const title = ref('Welcome on the index page!');
const text = ref('You are on the Buglopedia application page! Specially created for the JS Nation Workshop on June 13, 2022. Click on \'Generate bug\' to Generate a new bug and learn a lot about these creepy crawlies!')
</script>
