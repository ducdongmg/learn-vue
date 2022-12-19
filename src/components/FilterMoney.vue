<template>
    <div>
        <h2>Money Format</h2>

        {{money | filters}} 
        <input type="button" v-model="btnName" />

    </div>
</template>

<script>

export default {
    data() {
        return {
            money: 1000000,
            btnName: 'format'
        }
    },
    filters: {
        formatMoney(moneyVal) {
            return moneyVal.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
