<template>
  <li>
    {{book.title}} : {{book.author}}
    <span class="pill pass" v-if="book.finishedReading">Read</span>
    <span class="pill fail" v-else>Not Read</span>
  </li>
</template>

<script>
export default {
  name: "BookItem",
  props: ["book"],
};
</script>

<style>
li {
  display: block;
  margin: 1rem 10px;
}
.pill {
  border-radius: 5px;
  font-size: 0.65rem;
  padding: 0.25rem;
  text-align: center;
}
.pass {
  background: #41b883;
  color: white;
}
.fail {
  background: #ff7474;
  color: white;
}
</style>