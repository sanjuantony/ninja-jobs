<template>
    <div v-if="jobs.length">
        <div v-for="job in jobs" :key="job.id">
            <!-- <h2>{{ job.title }}</h2> -->
            <router-link :to="{ name: 'JobDetails', params: { id: job.id } }"> 
                {{job.title}} 
            </router-link>
        </div>
    </div>
    <div v-else>
            <p>Loading jobs...</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                // {title: "Ninja Web Designer", id: 1, details: "Ninja Web Designer Details"},
                // {title: "Ninja Web Developer", id: 2, details: "Ninja Web Developer Details"},
                // {title: "Ninja Web Architect", id: 3, details: "Ninja Web Architect Details"},
            ]
        }
    },
    mounted() {
        fetch("http://localhost:3000/jobs")
            .then((res) => res.json())
            .then((data) => this.jobs = data)
            .catch((err) => console.log(err.message))
    }
}
</script>

<style>

</style>