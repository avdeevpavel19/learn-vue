<template>
  <div class="app">
    <h3>Создать пост</h3>
    <form>
      <input class="input" type="text"
             placeholder="Введите название">
      <input class="input" type="text"
             placeholder="Введите контент">
      <button class="btn">Добавить</button>
    </form>

    <div class="posts">
      <h3>Список постов</h3>

      <div class="post">
        <div><strong>Название:</strong> это название поста</div>
        <div><strong>Контент:</strong> это контент поста</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
  width: 80%;
  margin: 0 auto;

}

form {
  display: flex;
  flex-direction: column;
}

.input {
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
  width: 100%;
}

.btn {
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
  cursor: pointer;
  margin-top: 15px;
  width: 100%;
}

.posts {
  margin-top: 50px;
}

.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 10px;
}
</style>
