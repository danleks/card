<template>
<div class="col-md-2">

    <!-- <h3>This is card No. {{ card.id }}</h3>
    <p>{{ card.content }}</p> -->
    <div class="card-deck">
     <div class="card bg-warning " @click="removeCard(card.id)">
         <div class="card-header">
             <p class="card-text">
                  {{ card.content }}
             </p>
         </div>
        <div class="card-body">
            <p class="card-text">

                My unique # is {{ card.id }}
            </p>
        </div>
    </div>
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

    props: ['cards', 'card', 'progress'],

    methods: {
        removeCard(id) {

            if (this.cards.length === 1) {
                return;
            }

            let index = this.cards.findIndex(card => card.id === id);
            this.cards.splice(index, 1);




        }
    }
}
</script>


<style lang="scss" scoped>
    .card-custom {
        display: inline-block;
        width: 18%;

        background-color: #f99557;
        padding: 20px;
        color: #fff;

        &:not(:last-child) {
            margin-right: 2%;
        }

    }
</style>