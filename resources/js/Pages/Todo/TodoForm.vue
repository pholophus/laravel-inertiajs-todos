<template>
  <div class="py-12">
    <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
      <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg p-6">
        <form
          @submit.prevent="
            form.post(route('todos.store'), {
              onSuccess: () => form.reset(),
            })
          "
        >
          <input
            class="form-control"
            type="text"
            placeholder="Task Name"
            v-model="form.task"
          />
          <div v-if="form.errors.task">{{ form.errors.task }}</div>
          <br />
          <button
            class="btn btn-primary"
            type="submit"
            :disabled="form.processing"
          >
            Add Task
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: this.$inertia.form({
        task: null,
      }),
    };
  },
};
</script>

<style>
</style>
