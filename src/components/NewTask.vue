<template>
    <div class="row">
        <form action="">
            <div class="col-sm-8.col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Task</label>
                <textarea class="form-control" rows="3" v-model="task"></textarea>
            </div>
            <div class="col-sm-8.col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add task</button>
            </div>
        </form>
        
    </div>
</template>
<script>
export default {
    data: function(){
        return {
            task: ''
        }
    },
    methods: {
        createNew(){
            this.$emit('taskAdded', this.task);
            this.task = '';
        }
    }
}
</script>
<style scoped>

</style>