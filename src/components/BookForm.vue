<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value placeholder="Book Title" />
    <input v-model="bookData.bookAuthor" type="text" name="author" value placeholder="Book Author" />
    <div>
      <input
        type="checkbox"
        id="finishedReading"
        name="finishedReading"
        v-model="bookData.finishedReading"
      />
      <label for="finishedReading">Finished Reading</label>
    </div>
    <div>
      <input
        id="borrowed"
        name="ownership"
        type="radio"
        v-model="bookData.ownership"
        value="borrowed"
      />
      <label for="borrowed">Borrowed</label>
      <input id="bought" name="ownership" type="radio" v-model="bookData.ownership" value="bought" />
      <label for="bought">Bought</label>
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: [],
      },
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    },
  },
};
</script>

<style>
label {
  user-select: none;
}
</style>
