<template>
    <div class="row">
        <div class="col-sm-12">
            <h2 class="mt-5">Cards Added</h2>
            <div class="progress">
                <div class="progress-bar bg-info">{{ progressCount }} / 5</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            progressCount: 1
        }
    }
}
</script>


<style lang="scss" scoped>
    .progress {
        height: 35px;

        &-bar {
            width: 20%;
            height: 35px;
        }
    }
</style>
