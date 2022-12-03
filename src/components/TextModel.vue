<template>
    <div>
        
        <input type="text" v-model="textContent" />
        <input type="text" v-model="chanel.value" />
        <input type="text" v-model="arrVal[0]" />

    </div>
</template>

<script>
export default {
    data() {
        return {
            textContent: "this is a text will show on input",
            chanel: {
                name: "vtv",
                value: 24
            },
            arrVal: [
                'arr 1',
                'arr 2',
            ]
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .className {
        color: red;
    }
</style>
