<template>
    <div id="app">
      <h1>Vue Async Components Demo</h1>

      <img src="https://via.placeholder.com/600x200.png?text=Lede%20Image" />
      <img src="https://via.placeholder.com/600x200.png?text=Lede%20Image" />
      <img src="https://via.placeholder.com/600x200.png?text=Lede%20Image" />

      <button @click="toggleDropdown">
          Click to toggle the dropdown content
      </button>
      <DropdownContent v-if="showDropdown" />

      <ImageContent1 />

      <ImageContent2 />
    </div>
</template>

<script>
import DropdownContent from './DropdownContent.vue';
import ImageContent1 from './ImageContent1.vue';
import ImageContent2 from './ImageContent2.vue';

export default {
    name: 'app',
    components: {
        DropdownContent,
        ImageContent1,
        ImageContent2,
    },
    data() {
        return {
            showDropdown: false,
        };
    },
    methods: {
        toggleDropdown() {
            this.showDropdown = !this.showDropdown;
        },
    },
}
</script>

<style scoped>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

img {
    display: block;
    max-width: 100%;
    margin: auto;
    padding: 20px;
}
</style>
