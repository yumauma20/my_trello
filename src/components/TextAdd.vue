<template>
    <form class="addtext" @submit.prevent="addTextToCard">
        <input v-model="body"
                type="text"
                class="text-input-card"
                placeholder="Add new text"
        />
        <button type="submit"  class="add-button-text">
            Add
        </button>     
    </form>
</template>

<script>
export default {
    props: {
        listIndex: {
            type: Number,
            required: true,
        }
    },
    data: function() {
        return {
            body: '',
        }
    },
    methods: {
        addTextToCard: function() {
            this.$store.dispatch('addTextToCard', { body: this.body, listIndex: this.listIndex })
        }
    }
}
</script>