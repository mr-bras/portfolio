<script>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
import TextEditor from './components/TextEditor.vue';
import LoginForm from './components/LoginForm.vue';
import MemGenTemplate from './components/MemGenTemplate.vue';
import TodoList from './components/TodoList.vue';
export default {
  components: {
    AppHeader,
    AppFooter,
    TextEditor,
    LoginForm,
    MemGenTemplate,
    TodoList
  }
}
</script>

<template>
  <app-header></app-header>
  <h1 style="text-align: center;">#1 todo list</h1>
  <todo-list></todo-list>
  <h1 style="text-align: center;">#2 text editor</h1>
  <text-editor></text-editor>
  <h1 style="text-align: center;">#3 login form</h1>
  <p style="text-align: center;">(для сообщения об успешном входе логин admin пароль 1234)</p>
  <login-form></login-form>
  <app-footer></app-footer>
</template>

<style scoped></style>
