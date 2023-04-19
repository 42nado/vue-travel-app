<script>
// import { RouterLink, RouterView } from 'vue-router';
import TheNavigation from './components/TheNavigation.vue';

export default {
  name: 'App',
  components: {
    TheNavigation
  }
};
</script>

<template>
    <div class="wrapper">
          <TheNavigation />
          <router-view :key="$route.path" ></router-view>
    </div>
</template>

