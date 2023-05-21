<template>
    <div class="wrapper">

        <nav>
            <p>Vue Travel</p>
            <ul>
                <li><RouterLink to="/">Home</RouterLink></li>
                <li v-for="destination in destinations" :key="destination.name">
                    <RouterLink :to="{ name: 'DestinationDetails', params: { slug: destination.slug } }">
                        {{ destination.name }}
                    </RouterLink>
                
                </li>
                <li><RouterLink to="/about">About</RouterLink></li>
            </ul>
            

            
        </nav>
    </div>
</template>
<script>
import store from "@/store.js";
export default {
    components: {},
    data() {
        return {
            destinations: store.destinations
        };
    }
};

</script>
<style scoped>
header {
    line-height: 2.5;
    max-height: 100vh;
}

nav {
    width: 100%;
    font-size: 20px;
    text-align: center;
    margin-top: 1rem;
    
}

nav a.router-link-exact-active {
    color: var(--color-text);
}

nav a.router-link-exact-active:hover {
    background-color: transparent;
}
li{
    list-style: none;
    margin: 0 1rem;
    display: inline-block;
    padding: 0 1rem;
    border-left: 1px solid var(--color-border);
    text-decoration: none;
}


nav a:first-of-type {
    border: 0;
}
</style>