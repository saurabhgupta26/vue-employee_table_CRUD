<template>
  <div id="employee-form">
    <form @submit.prevent="handleSubmit">
      <label>Employee Name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="email" />
      <button v-on="submit">Add Employee</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "employee-form",
  data() {
    return {
      employee: {
        name: "",
        email: "",
      },
    };
  },
  methods: {
    handleSubmit() {
      this.$emit('add:employee', this.employee)
    },
  },
};
</script>

<style>
form {
  margin-bottom: 2rem;
}
</style>