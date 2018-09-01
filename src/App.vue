<template>
  <div class="container">
    <app-progress :cards="cards" :progress="progressOn()"></app-progress>
    <app-input :cards="cards" :progress="progressOn()">

    </app-input>
    <div class="row">

      <app-card v-for="card in cards" :key="card.id" :cards="cards" :card="card" :progress="progressOn()"></app-card>

    </div>
    <app-info></app-info>
  </div>
</template>

<script>

import Progress from './components/Progress.vue';
import Input from './components/Input.vue';
import Card from './components/Card.vue';
import Info from './components/Info.vue';

import { BusEvent } from './main.js';



export default {
  data: function() {
    return {
      cards: [
        {id: 1, content: 'Hey, I am a card'}
      ],

      progressCount: 1,
      step: 1,
      width: 16.8
    }
  },
    components: {
        'app-progress': Progress,
        'app-input': Input,
        'app-card': Card,
        'app-info': Info
    },

    methods: {


       progressOn() {

                if (this.cards.length > this.step) {

                    //console.log(`Step is ${this.step}, length is ${this.cards.length}`);
                    this.step += 1;
                    this.progressCount++;
                    this.width += 16.8;


                } else if (this.cards.length < this.step) {
                    //console.log(`Step is ${this.step}, length is ${this.cards.length}`);
                    this.step -= 1;
                    this.progressCount--;
                    this.width -= 16.8;


                }

                BusEvent.$emit('progress', this.progressCount);
                BusEvent.$emit('width', this.width);


        }


    }
}
</script>


<style lang="scss">

</style>