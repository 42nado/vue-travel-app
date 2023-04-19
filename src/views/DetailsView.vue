<script>
// @ is an alias to /src
import store from "@/store.js";
export default {
    data() {
        return {
            destinationsId: this.$route.params.id
        }
    },
    computed: {
        destination() {
            return store.destinations.find(
                destination => destination.id == this.destinationsId
            )
        }
    }
}
</script>

<template>
    <section>
        <h1>{{ destination.name }}</h1>
        <div class="destination-details">
            <!-- {{ destination.image }} -->
            <img :src="`/src/assets/${destination.image}`" :alt="destination.name"/>
            <p>{{ destination.description }}</p>
        </div>
    </section>
</template>

<style scoped>
img{
    max-width: 600px;
    height: auto;
    width: 100%;
    max-height: 400px;
}
.destination-details{
    display: flex;
    justify-content: space-between;

}
p{
    margin: 0 40px;
    font-size: 20px;
    text-align: left;
}
h1{
    text-align: center;
    margin-top: 1rem;
}
</style>


