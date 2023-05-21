<script >
import store from "@/store.js";
export default {
  name: 'HomeView',
  components: {},
  data() {
    return {
      destinations: store.destinations
    }
  }
};
</script>

<template>
  <section>
    <h1>All Destinations</h1>
    <div class="content" >
    <div class="card" v-for="destination in destinations" :key="destination.name">
      <router-link :to="{ name: 'DestinationDetails', params: { slug: destination.slug } }">
      <img :src="`/src/assets/${destination.image}`" :alt="destination.name" style="width:100%">
      <div class="container">
        <h4><b>{{ destination.name }}</b></h4>
      </div>
    </router-link>
    </div>
    </div>
    
  </section>
</template>
<style scoped>
h1 {
  text-align: center;
  margin-top: 1rem;
}
.content {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.card {
  margin: 20px 10px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 400px;
  border-radius: 5px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

img {
  border-radius: 5px 5px 0 0;
}

.container {
  padding: 10px 16px;
}
</style>