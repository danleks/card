<template>
    <div class="row" slot="app-input">
        <div class="col-sm-12">
            <div class="form-group mt-5">

                <label for="input">Card description</label>
                <input :placeholder="placeholder" @keyup.enter="addCard" v-model="userText" class="form-control form-control-lg" name="input" />
                <button @click="addCard" type="button" class="btn btn-info btn-block mt-3">Add Card</button>

            </div>
        </div>
    </div>

</template>

<script>


import { BusEvent } from '../main.js';

export default {
    data: function() {
        return {
            userText: '',
            placeholder: ''
        }
    },

    props: ['cards'],

    methods: {
        addCard() {

            if (this.userText === '') {
                //this.userText = 'Type something';
                this.placeholder = 'Type in some text';

                return
            }


            if (this.cards.length != 6) {
                let ID = this.cards[this.cards.length-1].id + 1;
                this.cards.push(
                    {id: ID, content: this.userText}
                );
                this.userText = "";

                
            }

            


        }
    }
}
</script>


<style lang="scss" scoped>
  
</style>