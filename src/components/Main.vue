<template>
  <div>
    <navigateSideBar :username="username" class="sidebar" />
    <div class="content">
      <el-button class="back-button" @click="backConfirm" round>Back</el-button>
      <TodoTitle :title="title" subTitle="Simple Todo List with adding and filter by diff status." />
      <ToDoList />
      <filterButton class="filterButton" />
    </div>
  </div>
</template>

<script>
import ToDoList from "./ToDoList";
import TodoTitle from "./TodoTitle";
import filterButton from "./filterButton";
import navigateSideBar from "./navigateSideBar";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    ToDoList,
    TodoTitle,
    filterButton,
    navigateSideBar
  },
  beforeRouteLeave(to, from, next) {
    if (to.path === "/") {
      this.$confirm("将返回欢迎界面, 是否继续?", "提示", {
        confirmButtonText: "确定",
        cancelButtonText: "取消",
        type: "warning"
      })
        .then(() => {
          next();
          this.$message({
            type: "success",
            message: "已返回!"
          });
        })
        .catch(() => {
          next(false);
          this.$message({
            type: "info",
            message: "已取消返回"
          });
        });
    }
    else next();
  },
  methods: {
    backConfirm() {
      return this.$router.push("/");
    }
  },
  computed: {
    username() {
      return this.$route.params.username;
    },
    title() {
      return `${this.username}'s To Do List`;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
p {
  font-style: italic;
}
.back-button {
  text-align: left;
}
.content {
  float: left;
  margin-left: 680px;
} 
</style>
