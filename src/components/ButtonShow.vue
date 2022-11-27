<template>
    <div>
        <h2 v-show="isShow">this is the element we want to coltrol</h2>

        <button @click="isShow = !isShow" > show / hide</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isShow : true
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
