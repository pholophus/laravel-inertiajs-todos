<template>
  <div class="py-2">
    <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
      <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg p-6">
        <table class="table table-striped text-center">
          <thead>
            <tr>
              <th>Todo</th>
              <th>Action</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(task, index) in tasks" :key="index">
              <td>{{ task.todo }}</td>
              <td>
                <button class="btn btn-warning" @click="editTask(task)">
                  Edit
                </button>
                <button class="btn btn-danger" @click="deleteTask(task)">
                  Delete
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
  methods: {
    editTask(task) {
      console.log("task", task);
      this.$inertia.get(route("todos.edit", task.id));
    },
    deleteTask(task) {
      console.log("task", task);
      this.$inertia.delete(route("todos.destroy", task.id), {
        onSuccess: () => {
          console.log("success");
        },
      });
    },
  },
};
</script>

<style>
</style>
