<template>
    <div class="popup">
        <input v-model="value" type="number" placeholder="Value">
        <input v-model="category" type="text" placeholder="Category">
        <button class="green" v-on:click="onSaveClick">Add</button>
    </div>
</template>


<script>
export default {
    name: 'expensesAddForm',
    data() {
        return {
            value: '',
            category: ''
        }
    },
    computed: {
        getCurrentDate() {
            const today = new Date()
            const d = today.getDate()
            const m = today.getMonth() + 1
            const y = today.getFullYear()
            return `${d}.${m}.${y}`
        }
    },
    methods: {
        onSaveClick() {
            const data = {
                value: +this.value,
                category: this.category,
                date: this.date || this.getCurrentDate,
            }
            this.$emit('addNewPayment', data)
        }
    }
}
</script>



<style lang="scss">
.popup {
    background-color: rgb(153, 143, 132);
    border-radius: 10px;
    width: 550px;
    padding: 20px;
    position: absolute;
    top: 300px;
    left: calc(50% - 300px);

    input {
        margin-right: 10px;
        border-radius: 5px;
    }
}
</style>