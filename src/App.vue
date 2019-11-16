<template>
    <div class="container">
        <app-header :taskCount="tasks.length" :maxTasks="maxTasks"></app-header>
         <app-new-task @taskAdded="newTask"></app-new-task>
         <app-task-grid :tasks="tasks" @taskDeleted="deleteTask2"></app-task-grid>
         <div class="row">
             <div class="col-sm-12 text-center">
                 <div class="alert alert-info">Info: Click on a Task to delete it!</div>
             </div>
         </div>
    </div>
</template>

<script>
    import TaskGrid from './components/TaskGrid.vue';
    import NewTask from './components/NewTask.vue';
    import Header from './components/Header.vue';

    export default {
        data: function(){
            return {
                tasks: [
                    'Just one task to see'
                ],
                maxTasks: 10
            }
        },
        methods: {
            newTask(task) {
                if(this.tasks.length >= this.maxTasks){
                    return alert('Too many tasks. Finish one first');
                }
                this.tasks.push(task);
            },
            deleteTask2(index){
                this.tasks.splice(index,1);
            }
        },
        components: {
            appTaskGrid: TaskGrid,
            appNewTask: NewTask,
            appHeader: Header
        }
        
    }
</script>

<style>
</style>
