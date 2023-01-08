<template lang="">
    <div>
        All: {{allTodosCount}} Completed: {{completedTodosCount}} Pending: {{pendingTodosCount}}
    </div>
</template>
<script>
import { useTodoStore } from '../stores/TodoStore';
import { mapState } from 'pinia';

export default {
    name: 'MenuSection',
    computed: {
        ...mapState(useTodoStore, ['allTodosCount','pendingTodosCount','completedTodosCount']),
    }
}
</script>
<style lang="">
    
</style>