<template>
   <div>
     {{ msg }}
    <form>
      <button>Add Task</button>
      <button>Delete Finished Tasks</button>
      <p>input: <input type="text"></p>
      <p>task: </p>
    </form>
    <div class="task-list">
      <label class="task-list__item" v-for="todo in todos">
        <input type="checkbox"><button>Edit</button>{{ todo.text }}
      </label>
    </div>
   </div>
 </template>

<script>
export default {
  name: 'hello',
  data (){
    return {
      msg: 'Welcome to Your Vue.js App',
      todos : [
        {}
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@mixin flex-vender() {
  display: flex;
  display: -webkit-flex;
  display: -moz-flex;
  display: -ms-flex;
  display: -o-flex;
}
.task-list {
   @include flex-vender;
  flex-direction: column;
  align-items: center;
  &__item {
    width: 270px;
    text-align: left;
    $element: #{&};
    &--checked {
      @extend #{$element};
      color: #85a6c6;
    }
  }
}
</style>
