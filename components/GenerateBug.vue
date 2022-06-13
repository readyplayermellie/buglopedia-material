<template>
  <div id="detail-container">
    <img id="buglopedia-background" src="~/assets/images/background-dark-red.png"/>
    <img id="bug-image" :src="state.bugDetails.image" alt="bug-1" />
    <p id="bug-name">{{ state.bugDetails.name }}</p>
    <p id="bug-description">{{ state.bugDetails.description }}</p>
    <a id="generate-bug-button" @click="generateBug">Generate new bug</a>
  </div>
</template>

<script setup>
const state = reactive({
  bugDetails: {
    name: 'Ant',
    image: 'https://images.pexels.com/photos/1104974/pexels-photo-1104974.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
    description: 'Ant, (family Formicidae), any of approximately 10,000 species of insects (order Hymenoptera) that are social in habit and live together in organized colonies. Ants occur worldwide but are especially common in hot climates. They range in size from about 2 to 25 mm (about 0.08 to 1 inch). Their colour is usually yellow, brown, red, or black. A few genera (e.g., Pheidole of North America) have a metallic lustre. Typically, an ant has a large head and a slender, oval abdomen joined to the thorax, or midsection, by a small waist. In all ants there are either one or two finlike extensions running across the thin waist region. The antennae are always elbowed. There are two sets of jaws: the outer pair is used for carrying objects such as food and for digging, and the inner pair is used for chewing. Some species have a powerful sting at the tip of the abdomen.'
  }
});

const { data } = await useFetch('/api/bugs');

function generateBug() {
  state.bugDetails = data.value[Math.floor(Math.random() * data.value.length)];
}

</script>