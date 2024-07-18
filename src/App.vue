<script setup>
import { onBeforeMount, onMounted, ref } from 'vue'

const newTaskInput = ref(null);

onMounted(() => {
  newTaskInput.value.focus();
});

onBeforeMount(() => {

})
</script>

<template>

  <div style="max-width: 60%; margin: 3rem auto;">
    <form>
      <!-- Adding tasks form -->
      <input ref="newTaskInput" placeholder="Add new task">
      <select>
        <option disabled value="">Select priority</option>
        <option>High</option>
        <option>Medium</option>
        <option>Low</option>
      </select>
      <button type="submit">Add Task</button>
    </form>

    <!-- Task filtering -->
    <input placeholder="Filter tasks...">

    <!-- If there no tasks -->
    <div>
      <p>No tasks found. Try changing the filter or add some tasks!</p>
    </div>

    <div>
      <h3>Your Tasks</h3>
      <!-- This is a list of tasks -->
      <div>
        <div>
          <!-- Is task done? -->
          <input type="checkbox">
          <!-- Task description -->
          <span></span>
        </div>
        <!-- Removing a task -->
        <button class="remove-button">✖</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
body {
  font-family: 'Arial', sans-serif;
  padding: 20px;
  font-size: 16px;
  background-color: #f4f4f9;
}

.task {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: white;
  padding: 10px 20px;
  margin-bottom: 10px;
  border-radius: 5px;
  border-left: 5px solid;
}

.high {
  border-color: red;
}

.medium {
  border-color: orange;
}

.low {
  border-color: green;
}

.completed {
  text-decoration: line-through;
  color: #bbb;
}

.remove-button {
  color: red;
  cursor: pointer;
  border: none;
  background: none;
  font-size: 16px;
}
</style>
