<template>
  <h1>Job Details Page</h1>
  <p>The job ID is: {{ $route.params.id }}</p>
  <p>The job ID is: {{ _id }}</p>
</template>

<script>
export default {
    data() {
        return {
            _id: this.$route.params.id
        }
    }
}
</script>

<style>

</style>