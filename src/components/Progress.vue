<template>
    <div class="row">
        <div class="col-sm-12">
            <h2 class="mt-5">Cards Added</h2>
            <div class="progress">
                <div class="progress-bar bg-info" v-bind:style="{width: width + '%'}"> {{ progressCount }}  / 6</div>
            </div>
        </div>
    </div>
</template>

<script>

import { BusEvent } from '../main.js';


export default {
    data: function() {
        return {
            progressCount: 1,
            width: 16.8
        }
    },

    props: ['cards', 'progress'],

    created() {
        BusEvent.$on('progress', (e) => {
            this.progressCount = e;
        })

        BusEvent.$on('width', (e) => {
            this.width = e;
        })

    }
}
</script>


<style lang="scss" scoped>
    .progress {
        height: 35px;

        &-bar {
            width: 16%;
            height: 35px;
        }
    }
</style>
