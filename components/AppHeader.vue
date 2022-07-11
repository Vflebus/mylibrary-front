<template>
  <header>
    <h1>Ma Librairie</h1>
    <input v-model="search" type="search" placeholder="Chercher un livre" class="searchInput" autocomplete="off" @input="triggerBookFiltering" />
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
  data() {
    return {
      search: '',
    }
  },
  methods: {
    triggerBookFiltering() {
      this.$emit('filter', this.search);
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  width: 100vw;
  height: 20vh;
  background-color: rgb(240, 148, 0);
  display: flex;
  flex-direction: column;
  row-gap: 5%;
  justify-content: center;
  align-items: center;
  color: #191919;
  font-size: 2rem;
  position: sticky;
  top: 0;
  left: 0;
}
</style>
