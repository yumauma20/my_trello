<template>
    <div class="card">
        <button class="close-button" @click="removeCardFromList">
            ×
        </button>
        <div class="body">
            {{ body }}
        </div>
        <text-add :listIndex="listIndex" />
    </div>
</template>

<script>
import TextAdd from './TextAdd'

export default {
    components: {
        TextAdd
    },
    props: {
        body:{
            type: String,
            required: true
        },
        listIndex: {
            type: Number,
            required: true
        },
        cardIndex: {
            type: Number,
            required: true
        }
    },
    methods: {
        removeCardFromList() {
            if(confirm('本当にこのカードを削除しますか？')) {
                this.$store.dispatch('removeCardFromList', { cardIndex: this.cardIndex, listIndex: this.listIndex})
            }
        }
    },
}
</script>