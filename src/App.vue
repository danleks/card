<template>
  <div class="container">
    <app-progress></app-progress>
    <app-input :cards="cards">

    </app-input>
    <div class="row">
       <div class="col-sm-12">
      <app-card v-for="card in cards" :key="card.id" :cards="cards" :card="card"></app-card>
      </div>
    </div>
    <app-info></app-info>
  </div>
</template>

<script>

import Progress from './components/Progress.vue';
import Input from './components/Input.vue';
import Card from './components/Card.vue';
import Info from './components/Info.vue';

export default {
  data: function() {
    return {
      cards: [
        {id: 1, content: ' This is the first default card. Feel free to add some more custom cards!'}
      ]
    }
  },
    components: {
        'app-progress': Progress,
        'app-input': Input,
        'app-card': Card,
        'app-info': Info
    }
}
</script>


<style lang="scss">

</style>