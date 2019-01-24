<template>
    <div id="app">
      <h1>Vue Async Components Demo</h1>

      <div>
          <img src="https://via.placeholder.com/600x200.png?text=Lede%20Image" />
      </div>

      <button @click="toggleDropdown">
          Click to toggle the dropdown content
      </button>
      <DropdownContent v-if="showDropdown" />

    </div>
</template>

<script>
import ErrorMessage from './ErrorMessage.vue';
import LoadingSpinner from './LoadingSpinner.vue';

export default {
    name: 'app',
    components: {
        DropdownContent: () => ({
            component: import('./DropdownContent.vue'),
            loading: LoadingSpinner,
            error: ErrorMessage,
        }),
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

<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    margin-bottom: 300px;
}

div {
    width: 100;
    padding: 20px;
}

img {
    display: block;
    width: 100%;
}
</style>
