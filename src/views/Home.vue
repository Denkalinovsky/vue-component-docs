<template>
  <div class="home">
    <div class="container">
      <div>Add todo:</div>
      <el-button @click="dialogVisible = true" type="primary"
      >Primary
      </el-button>
      <ol>
        <li v-for="todo in todos" :key="todo.text">
          {{ todo.text }}
        </li>
      </ol>
    </div>
    <el-dialog
      v-model="dialogVisible"
      title="Tips"
      width="30%"
      :before-close="handleClose"
    >
      <span>Add new todo</span>
      <template #footer>
      <span class="dialog-footer">
        <el-button @click="dialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="NotificationSuccessful">Confirm</el-button>
      </span>
      </template>
    </el-dialog>
  </div>
</template>

<script>
import { ElNotification } from "element-plus";

export default {
  name: "Home",
  data() {
    return {
      todos: [
        { text: "Learn JavaScript" },
        { text: "Learn Vue" },
        { text: "Build something awesome" }
      ],
      dialogVisible: false

    };
  },
  methods: {
    handleClose() {
      this.dialogVisible = false;
    },
    NotificationSuccessful() {
      this.dialogVisible = false;
      ElNotification({
        title: "Success",
        message: "This is a success message",
        type: "success"
      });
    }
  }
};
</script>
