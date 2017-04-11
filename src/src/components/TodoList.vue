<template>
  <div class="todo-list">
    <!-- new item input bar -->
    <div class="form-group">
      <div class="input-group">
        <!-- input box -->
        <input @keyup.enter="addTodoItem"
               v-model="newTodoItem"
               type="text"
               class="form-control"
               placeholder="Input new TODO item">
        <!-- add button -->
        <span @click="addTodoItem"
              class="input-group-btn">
                      <button type="button" class="btn btn-default" aria-label="Add new todo item">
                        <span class="glyphicon glyphicon-plus" aria-hidden="true"></span>
        </button>
        </span>
      </div>
    </div>
    <!-- todo item list -->
    <ul class="list-group">
      <!-- caption -->
      <a href="#"
         class="list-group-item active">Todo Items<span class="badge">{{todoItems.length}}</span></a>
      <!-- todo items -->
      <a v-for="(item, index) in todoItems"
         @click="makeTodoItemDone(index)"
         href="#"
         class="list-group-item">{{item}}</a>
    </ul>
    <!-- done item list -->
    <ul class="list-group">
      <!-- caption -->
      <a href="#"
         class="list-group-item list-group-item-success">Done Items<span class="badge">{{doneItems.length}}</span></a>
      <!-- done items -->
      <a v-for="(item, index) in doneItems"
         @click="reverDoneItem(index)"
         href="#"
         class="list-group-item text-muted todo-item-done">{{item}}</a>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data() {
    return {
      newTodoItem: '',
      todoItems: ['todo 1', 'todo 2', 'todo 3'],
      doneItems: ['done 4', 'done 5'],
    };
  },
  methods: {
    // Create new ID which is never been used.
    newId() {
      return this.todoItems.length + this.doneItems.length + 1;
    },
    addTodoItem() {
      const newTodoItem = this.newTodoItem.trim();
      if (newTodoItem !== '') {
        this.todoItems.unshift(this.newTodoItem);
        this.newTodoItem = '';
      }
    },
    makeTodoItemDone(index) {
      const doneItem = this.todoItems.splice(index, 1)[0];
      this.doneItems.unshift(doneItem);
    },
    reverDoneItem(index) {
      const undoneItem = this.doneItems.splice(index, 1)[0];
      this.todoItems.unshift(undoneItem);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todo-list {
  padding: 10px;
}

.todo-item-done {
  text-decoration: line-through
}

/* fade out */
.fade-enter-active,
.fade-leave-active {
  transition: opacity .5s
}

/* fade in */
.fade-enter,
.fade-leave-active {
  opacity: 0
}
</style>
