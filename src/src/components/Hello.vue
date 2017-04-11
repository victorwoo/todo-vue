<template>
  <div class="todo-list">
    <div class="form-group">
      <div class="input-group">
        <input type="text" class="form-control" placeholder="Input new TODO item">
        <span class="input-group-btn">
            <button type="button" class="btn btn-default" aria-label="Add">
              <span class="glyphicon glyphicon-plus" aria-hidden="true"></span>
            </button>
        </span>
      </div>
    </div>
    <ul class="list-group">
      <a href="#" class="list-group-item active">
          Todo Items
        </a>
      <a href="#" class="list-group-item">Dapibus ac facilisis in</a>
      <a href="#" class="list-group-item">Morbi leo risus</a>
      <a href="#" class="list-group-item">Porta ac consectetur ac</a>
      <a href="#" class="list-group-item">Vestibulum at eros</a>
    </ul>
    <ul class="list-group">
      <a href="#" class="list-group-item list-group-item-success">
          Done Items
        </a>
      <a href="#" class="list-group-item text-muted todo-item-done">Dapibus ac facilisis in</a>
      <a href="#" class="list-group-item text-muted todo-item-done">Morbi leo risus</a>
      <a href="#" class="list-group-item text-muted todo-item-done">Porta ac consectetur ac</a>
      <a href="#" class="list-group-item text-muted todo-item-done">Vestibulum at eros</a>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'hello',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
      };
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .todo-list {
    padding: 10px;
  }

  .todo-item-done {
    text-decoration:line-through
  }
</style>
