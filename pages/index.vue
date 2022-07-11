<template>
  <div class="app">
    <AppHeader @filter="filterBooks" />
    <div class="cardsContainer">
      <BookCard
        v-for="(book, index) in currentBookList"
        :key="index"
        :title="book.title"
        :image="book.image"
        :author="book.author"
        :summary="book.summary"
        :note="book.note"
        :date="book.dateOfCreation"
      />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'IndexPage',
  data() {
    return {
      books: [],
      currentBookList: [],
    }
  },
  async fetch() {
    await this.getAllBooks()
  },
  methods: {
    async getAllBooks() {
      const data = await axios.get('http://192.168.1.20:4000/')
      this.books = data.data
      this.currentBookList = this.books
    },
    filterBooks(search) {
      this.currentBookList = this.books.filter(function (obj) {
        return Object.keys(obj).some(function (key) {
          if (typeof obj[key] === 'string') {
            return obj[key].toLowerCase().includes(search.toLowerCase())
          }
          return false
        })
      })
    },
  },
}
</script>
