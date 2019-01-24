<template>
    <div id="app">
        <h1>Vue Async Components Demo</h1>

        <button @click="toggleDropdown">
            Click to toggle the dropdown content
        </button>

        <DropdownContent v-if="showDropdown" />
    </div>
</template>

<script>
import LoadingSpinner from './LoadingSpinner.vue';
import ErrorMessage from './ErrorMessage.vue';

export default {
    name: 'app',
    components: {
        DropdownContent: () => ({
            component: import('./DropdownContent.vue'),
            loading: LoadingSpinner,
            error: ErrorMessage,
            timeout: 3000,
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
