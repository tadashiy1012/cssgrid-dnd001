<template>
    <div id="bookTable">
        <template v-for="(book, idx) in books">
            <droppable :key="idx">
                <draggable>
                    <img :src="book" />
                </draggable>
            </droppable>
        </template>
    </div>
</template>
<script>
import Draggable from './Draggable.vue';
import Droppable from './Droppable.vue';
export default {
    computed: {
        books: function() { return this.$store.getters.books; }
    },
    components: {
        Draggable, Droppable
    }
}
</script>
<style scoped>
#bookTable {
    display: grid;
    grid-template-columns: repeat(3, 200px);
    grid-auto-rows: minmax(200px, auto);
    gap: 8px 8px;
}
#bookTable > div {
    justify-self: center;
    align-self: center;
}
</style>
