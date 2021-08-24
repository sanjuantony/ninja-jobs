<template>
    <div v-if="job">
        <h1>{{ job.title }}</h1>
        <p>The job ID from route params is: {{ $route.params.id }}</p>
        <p>The job ID from Props is: {{ this.id }}</p>
        <p>The job Description is: {{ job.details }}</p>
    </div>
    <div v-else>
        <p>Loading job description....</p>
    </div>
</template>

<script>
export default {
    props: ["id"],
    // data() {
    //         return {
    //             _id: this.$route.params.id
    //         }
    //     }
    // }
    mounted() {
        fetch("http://localhost:3000/jobs/"+this.id)
            .then((res) => res.json())
            .then((data) => this.job = data)
            .catch((err) => console.log(err.message))
    },
    data() {
        return {
            job: null
        }
    }
}
</script>

<style>

</style>