<template>
    <div class="list">
        <div class="item item-bold">
            <span>Date</span>
            <span>Category</span>
            <span>Value</span>
        </div>
        <div class="item" v-for="item of information" v-bind:key="item.id">
            <div>{{ item.date }}</div>
            <div>{{ item.category }}</div>
            <div>{{ item.value }} $</div>
        </div>
    </div>
</template>


<script>
export default {
    name: 'expensesList',  // название компонента
    props: {
        information: Array,   // передача данных
        default: []
    }
}
</script>


<style lang="scss">
.list {
    width: 1000px;
    margin: 50px auto;
    border-radius: 10px;
    background-color: rgb(230, 226, 221);
    margin-bottom: 20px;
    border-radius: 10px;

    .item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 10px 30px;
    }
}

.item-bold {
    font-weight: 700;
}
</style>