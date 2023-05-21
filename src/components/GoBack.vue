<template>
    <div>
        <span class="go-back">
            <button @click="goBack">Back</button>
        </span>
    </div>
</template>

<script>
export default {
    methods: {
        goBack() {
            return this.$router.go(-1);
        }
    }
};

</script>