<template>
  <ul>
    <li v-for="todo in $doneTodos" :key="todo.id">{{ todo.text }}</li>
  </ul>
</template>

<script>
export default {
  computed: {
    $allTodos() {
      return this.$store.getters.$allTodos
    },
    $doneTodos() {
      return this.$store.getters.$doneTodos
    }
  },

  created() {
    this.$store.dispatch('fetchTodos')
  }
}
</script>
