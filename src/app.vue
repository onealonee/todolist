<template>
  <div class="newPole">
    <label>Новая запись:</label>
    <input v-model="sborkaZadach">
    <button @click="addTask" class="btn">
      Добавить запись
    </button>
  </div>
  <div class="spisokZadach">

  </div>
</template>

<script>
export default {
  data() {
    return{
      a: [],
      sborkaZadach: ''
    }
  },
  methods: {
    addTask() {
      this.a.push({titl: this.sborkaZadach})
    }
  }
}
</script>

<style scoped>
.newPole {
  border:  2px solid black;
  padding: 10px;
  display: flex;
  justify-content: space-between;
}
.btn {
  margin-left: auto;
}
</style>