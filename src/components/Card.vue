<template>
    <div class="card bg-light card-custom" @click="removeCard(card.id)">
        <div class="card-header">This is card No. {{ card.id }}</div>
        <div class="card-body">
            <p class="card-text">
                {{ card.content }}
            </p>
        </div>
    </div>
</template>

<script>
export default {

    data: function() {
        return {
            deleteIsOn: false
        }
    },

    props: ['cards', 'card'],

    methods: {
        removeCard(id) {


                let index = this.cards.findIndex(card => card.id === id);
                this.cards.splice(index, 1);
                console.log(this.cards);

        }

        }
}
</script>


<style lang="scss" scoped>
    .card-custom {
        display: inline-block;
        width: 18%;

        &:not(:last-child) {
            margin-right: 2%;
        }

    }
</style>