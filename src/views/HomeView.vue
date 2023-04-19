<script >
import  store  from "@/store.js";
export default {
  name: 'HomeView',
  components: {},
    data(){
        return {
            destinations: store.destinations
        }
    }
};
</script>

<template>
  <main>
    <h1>Home</h1>
    <div class="destinations">
      <div class="destination" v-for="destination in destinations" :key="destination.id">
        <router-link :to="{name: 'DestinationDetails', params: {id: destination.id}}">
          <img :src="`/src/assets/${destination.image}`" :alt="destination.name"/>
          <h2>{{ destination.name }}</h2>
        </router-link>
      </div>
    </div>
  </main>
</template>
<style scoped>
img{
    max-width: 600px;
    height: auto;
    width: 100%;
    max-height: 400px;
}
.destination{
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px;
}
.destinations{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
h2{
    text-align: center;
    margin-top: 1rem;
}
h1{
    text-align: center;
    margin-top: 1rem;
}


</style>