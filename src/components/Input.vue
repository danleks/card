<template>
    <div class="row" slot="app-input">
        <div class="col-sm-12">
            <div class="form-group mt-5">
                <label for="card-content">Card description</label>
                <textarea @keyup.enter="addCard" v-model="userText" class="form-control" id="comment" rows="5"></textarea>
                <button @click="addCard" type="button" class="btn btn-info btn-block mt-3">Add Card</button>
            </div>
        </div>
    </div>

</template>

<script>
export default {
    data: function() {
        return {
            userText: '',
            addIsOn: true
        }
    },
    props: {
        cards: {
            type: Array
        }
    },
    methods: {
        addCard() {

            if (this.addIsOn) {


                let ID = this.cards[this.cards.length-1].id + 1;
                this.cards.push(
                    {id: ID, content: this.userText}
                );
                this.userText = "";
                console.log(this.cards);

                if (this.cards.length === 5) {
                    this.addIsOn = false;
                }

            }



        }
    }
}
</script>


<style lang="scss" scoped>

</style>