<template>
  <div class="container">
    <h2 class="text-center mt-5">My Vue Todo App</h2>

    <!-- input -->
    <div class="d-flex">
      <input
        v-model="task"
        type="text"
        placeholder="Enter task"
        class="form-control"
      />
      <button @click="submitTask" class="btn btn-warning rounded-0">
        Submit
      </button>
    </div>

    <!-- table -->
    <table class="table table-bordered mt-5">
      <thead>
        <tr>
          <th scope="col">Task</th>
          <th scope="col">Status</th>
          <th scope="col" class="text-center">#</th>
          <th scope="col" class="text-center">#</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(task, index) in tasks" :key="index">
          <td>{{ task.name }}</td>
          <td>{{ task.status }}</td>
          <td>
            <div class="text-center" @click="editTask(index)">
              <span class="fa fa-pen"></span>
            </div>
          </td>
          <td>
            <div class="text-center" @click="deleteTask(index)">
              <span class="fa fa-trash"></span>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { ref } from "vue";

const task = ref([]);

const editedTask= ref(null)

const tasks = ref([
  {
    name: "Steal bananas from the box",
    status: "to-do",
  },
  {
    name: "Buy some food",
    status: "in-progress",
  },
]);

function submitTask() {
  if (task.value.length === 0) return;

  if(editedTask.value === null) {
  tasks.value.push({
    name: task.value, 
    status: "to-do",
  });
  } else{
    tasks.value[editedTask.value].name = task.value;
    editedTask.value = null;
  }
  task.value = []; 
}

function deleteTask(index){
  tasks.value.splice(index, 1)
}

function editTask(index){
  task.value = tasks.value[index].name;
  editedTask.value = index;
}

</script>
