<template>
  <div id="employee-form">
    <form>
      <label>Employee name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="text" />
      <form @submit.prevent="handleSubmit">
        <button>Add Employee</button>
      </form>
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
      console.log("testing handleSubmit"), this.$emit("add:employee", this.employee);
    },
  },
};
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}
</style>
