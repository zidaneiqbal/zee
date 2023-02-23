<template>
  <div class="about">
    <div class="grid">
      <router-link class="cursor-pointer text-center" :to="{ name: 'about' }">
        About
      </router-link>
    </div>
    <img src="@/assets/prof.jpg" alt="Profile Picture" />
    <p>Bio</p>
    <ul>
      <li><strong>Name:</strong> {{ name }}</li>
      <li><strong>Location:</strong> {{ location }}</li>
      <li><strong>Age:</strong> {{ age }}</li>
    </ul>
  </div>
</template>
<script>
import { gsap } from "gsap";
export default {
  data() {
    return {
      name: "Zidane",
      age: "20",
      location: "Malang",
    };
  },
  mounted() {
    let tl = gsap.timeline();
    tl.from(".about", { opacity: 0, y: 150, duration: 2 });
  },
};
</script>

<style>
section {
  max-width: 800px;
  margin: auto;
  padding: 2rem;
}

.about img {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  margin: 1rem 0;
}
</style>
