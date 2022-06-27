<template>
  <div class="app">
    <AppHeader @filter="filterBooks" />
    <div class="cardsContainer">
      <div v-for="(book, index) in currentBookList" :key="index" class="card">
        <section class="imgContainer">
          <img :src="book.image" alt="" />
        </section>
        <section class="bookDescription">
          <h3 class="bookTitle">{{ book.title }}</h3>
          <p>{{ book.author }}</p>
          <p class="bookSummary">{{ book.summary }}</p>
          <p>Note: {{ book.note }}/5</p>
          <p>Année de parution: {{ book.dateOfCreation }}</p>
        </section>
      </div>
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
      this.books = []
      const data = await axios.get('http://192.168.1.20:1213/')
      data.data.forEach((book) => {
        this.books.push(book)
      })
      this.currentBookList = this.books
    },
    filterBooks(searchKey) {
      this.currentBookList = this.books.filter(function (obj) {
        return Object.keys(obj).some(function (key) {
          if (typeof obj[key] === 'string') {
            return obj[key].toLowerCase().includes(searchKey.toLowerCase());
          }
          return false
        })
      })
    },
  },
}
</script>
