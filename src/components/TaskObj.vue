<template>
    <div>
       <span> {{taskProp1.title}} </span>
    </div>
</template>

<script>
export default {
    // props : ['taskProp1', 'taskProp2'], // cách 1: định nghĩa mảng các prop muốn dùng và assign giá trị của nó từ phía gọi
    props: {
        taskProp1 : { // cách 2: define object
            type: Object,
            default: function() {
                return { title: 'My journey with Vue', status: false }
            }
        }
    },
    data() {
        return {
            newTask: '',
            
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
