<template>
    <div>
        <form action="/abc">
            <input ref="content" type="text" v-model="textContent" />
            <button type="submit" v-on:click.prevent="textContent = 'change value' " > click </button>
            <input type="text" v-model="this.$refs.content" />
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            textContent: "this is a text will show on input"
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
