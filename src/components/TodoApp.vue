<script setup></script>

<template>
  <div class="container">
    <h2 class="text-center mt-5">My Vue Todo App</h2>

    <!-- imput -->
    <div class="d-flex">
      <input type="text" placeholder="Enter task" class="form-control" />
      <button class="btn btn-warning rounded-0">Submit</button>
    </div>

    <!-- table  -->
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
        <tr>
          <td> Steal bananas from store. </td>
          <td>To-do</td>
          <td></td>
          <td></td>
        </tr>
      </tbody>

    </table>
  </div>
</template>

<style scoped></style>
