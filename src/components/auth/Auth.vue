<template>
  <div>
    {{ formattedTitle }}

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

    <button @click.prevent="updateLoginDetails">{{ formattedTitle }}</button>
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

  computed: {
    formattedTitle: function() {
      return this.formType[0].toUpperCase() + this.formType.slice(1);
    }
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