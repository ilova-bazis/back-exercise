<template>
    <div id="show-exercises">
        <div class="card mb-2" v-for="(item, index) in exercises" v-bind:key="item.id" v-bind:id="item.id">
            <div class="card-header bg-dark text-light">
                <h5 class="card-title">
                    Упражнение {{ item.id }}
                </h5>
                 <h6 class="card-subtitle mb-2 text-warning">
                    {{ item.position }}
                </h6>
                <button class="btn btn-light float-right" v-on:click="done(index)">Done</button>
            </div>
            <div class="card-body">


                <p class="card-text">
                    {{ item.description}}
                </p>
                
            </div>
            <div class="card-footer">
                   Повторить {{ item.repmin }} - {{ item.repmax }} раз
            </div>
        </div>
    </div>

</template>
<script>
export default {
    data() {
        return {
            name: "bazis",
            exercises: [],
            isActive: false
        }
    },
    methods: {
        done: function(id){
            this.exercises.splice(id, 1)
        }

    },
    created() {
        this.$http.get('exercises.json').then(function(data){
            
            this.exercises = data.body;
        })
    }
}
</script>
<style>
.exdone{
    visibility: hidden;
    
}
</style>
