<template>
  <div class="newPole">
    <label>Новая запись:</label>
    <input @keydown.enter="addTask" v-model="sborkaZadach">
    <button @click="addTask" class="btn">
      Добавить запись
    </button>
  </div>
  <div class="spisokZadach">

    <ul v-for="task in a">
      <li>{{task}}</li>
    </ul>
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
      this.a.push(this.sborkaZadach)
      this.sborkaZadach = ''
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
  border-radius: 15px;
}
.btn {
  margin-left: auto;
}

.spisokZadach{
  border: 2px solid black;
  padding: 15px;
  margin-top: 40px;
  border-radius: 15px;
}
</style>