<template>
  <div class="newPole">
    <label>Новая запись:</label>
    <input @keydown.enter="addTask" v-model="sborkaZadach">
    <button @click="addTask" class="btn">
      Добавить запись
    </button>
  </div>
  <div class="spisokZadach">
    <div class="output-container" v-for="task in a" :key="task">
      <p class="output">{{ task }}</p>
    </div>
  </div>
</template>

<script>
export default {
    data() {
      return{
        a: JSON.parse(localStorage.getItem('tasks')) || [], // При загрузке компонента, проверяем Local Storage на наличие сохраненных задач
        sborkaZadach: ''
      }
    },
    methods: {
      addTask() {
        this.a.push(this.sborkaZadach);
        this.sborkaZadach = '';
        localStorage.setItem('tasks', JSON.stringify(this.a)); // При каждом обновлении данных, сохраняем их в Local Storage
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

.output-container {
  border: 2px solid black; /* Обводка */
  padding: 10px; /* Отступ внутри контейнера */
  margin-top: 10px; /* Отступ сверху */
}

.output {
  
}
</style>
