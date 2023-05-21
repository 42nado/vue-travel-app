<script>
// @ is an alias to /src
import store from "@/store.js";
// import GoBack from "@/components/GoBack";
export default {
    // components:{
    //     GoBack
    // },
    data() {
        return {
            slug: this.$route.params.slug
        }
    },
    computed: {
        destination() {
            return store.destinations.find(
                destination => destination.slug == this.slug
            )
        }
    }
}
</script>

<template>
    <div>
        <!-- <GoBack /> -->
    <section>
        <h1>{{ destination.name }}</h1>
        <div class="destination-details">
            <!-- {{ destination.image }} -->
            <img :src="`/src/assets/${destination.image}`" :alt="destination.name" />
            <p>{{ destination.description }}</p>
        </div>
    </section>
    <section class="experiences">
        <h2>Top Experience in {{ destination.name }}</h2>
        <div class="cards">
            <div v-for="experience in destination.experiences" :key="experience.slug">
                <div class="card">
                    <router-link :to="{ name: 'experienceDetails', params: {experienceSlug: experience.slug}}">
                    <img :src="`/src/assets/${experience.image}`" :alt="experience.name">
                    <div class="card__text">
                        {{ experience.name }}
                    </div>
                </router-link>
                </div>
            </div>
        </div>
        <router-view :key="$route.path"></router-view>
    </section>
</div>
</template>

<style scoped>
img {
    max-width: 600px;
    height: auto;
    width: 100%;
    max-height: 400px;
}

.destination-details {
    display: flex;
    justify-content: space-between;
}

p {
    margin: 0 40px;
    font-size: 20px;
    text-align: left;
}

h2 {
    text-align: center;
}

.cards img {
    max-height: 200px;
}

.cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    padding-top: 20px;
}

.card {
    width: 300px;
    height: 200px;
    padding: 0 20px;
}

.card__text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color:white;
    font-size: 25px;
    font-weight: bold;
    text-decoration: none;
}

.experiences {
    margin-top: 50px;
}
</style>


