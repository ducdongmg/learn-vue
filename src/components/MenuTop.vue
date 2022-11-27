<template>
    <div>
        <h2>this is menu top ten</h2>

        <input type="text" v-model="name" />

        {{name}} 
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: "this is a name binding"
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
