<!-- eslint-disable eqeqeq -->
<!-- eslint-disable eqeqeq -->
<template>

  <q-page>
  <ul>
  <delete-task
   v-for="(task,index) in tasks"
    :task = "task"
    :index = "index"
    :key="task.id">{{task.name}}</delete-task>
  </ul>
  </q-page>

</template>

<script>
import DeleteTask from 'components/delete-task.vue'
export default {
  data () {
    return {
      tasks: [
        {
          id: '1',

          name: 'Go To Store',
          dueDate: '2023/12/16',
          dueTime: '14:40'
        },
        {
          id: '2',
          name: 'Get Apples',
          dueDate: '2023/12/22',
          dueTime: '16:40'
        },
        {
          id: '3',
          name: 'Go To Oranges',
          dueDate: '2023/12/25',
          dueTime: '20:00'
        }
      ]
    }
  },
  methods: {
    deleteTask (index) {
      this.tasks.splice(index, 1)
    }
  },
  components: {
    DeleteTask
  }
}

</script>
