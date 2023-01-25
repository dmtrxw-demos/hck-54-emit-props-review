<script>
// App.vue
//   - foods []
//   - <Table :foods="foods" />

    // Table.vue
    //   - props ['foods']
    //   - <TableRow v-for="food in foods" :food="food" :key="food.id" />

        // TableRow.vue
        //   - props ['food']

import Card from './components/Card.vue'

export default {
    // State
    data() {
        return {
            foods: [],
        }
    },
    // Component registration
    components: {
        Card,
    },
    
    methods: {
        deleteFood(id) {
            console.log('Card menyuruh deleteFood', id)
        }
    },

    // Lifecycle
    // Ketika component sudah berhasil dibuat/render
    created() {
        // Fetch food data
        const foods = [
            { id: 1, title: 'Ayam goreng', description: 'Ayam goreng enak sekali' },
            { id: 2, title: 'Burger', description: 'Burger enak' },
            { id: 3, title: 'Pizza', description: 'Makanan italia' },
        ]

        this.foods = foods
    },
}
</script>

<template>
    <Card
        v-for="food in foods"
        :item="food"
        @deleteFood="deleteFood" />
</template>

<style></style>
