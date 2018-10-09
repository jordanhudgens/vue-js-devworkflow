<template>
  <div>
    {{ formType }}

    <form>
      <div v-if="formType === 'register'">
        <label>Name</label>
        <input type="text" v-model="name">
      </div>

      <div>
        <label>Email</label>
        <input type="text" v-model="email">
      </div>

      <div>
        <label>Password</label>
        <input type="password" v-model="password">
      </div>
    </form>

    <button @click.prevent="updateLoginDetails">Login</button>
  </div>
</template>

<script>
export default {
  name: 'Auth',
  data() {
    return {
      email: '',
      password: '',
      name: ''
    }
  },

  props: {
    formType: String
  },

  methods: {
    updateLoginDetails() {
      this.$emit('update', this.email);
    }
  }
}
</script>

<style scoped>

</style>