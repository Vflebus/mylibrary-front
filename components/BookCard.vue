<template>
  <div class="card">
    <section class="imgContainer">
      <img :src="image" alt="" />
    </section>
    <section class="bookDescription">
      <h3 class="bookTitle">{{ title }}</h3>
      <p>{{ author }}</p>
      <p class="bookSummary">{{ summary }}</p>
      <p>Note: {{ note }}/5</p>
      <p>Année de parution: {{ date }}</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'BookCard',
  props: {
    title: { type: String, default: '' },
    image: { type: String, default: '' },
    author: { type: String, default: '' },
    summary: { type: String, default: '' },
    note: { type: Number, default: 0 },
    date: { type: Number, default: null },
  },
}
</script>

<style lang="scss" scoped>
.card {
  width: 80%;
  height: 70vh;
  border-radius: 30px;
  overflow: hidden;
  border: 1px white solid;

  .imgContainer {
    width: 100%;
    height: 40%;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    img {
      min-width: 100%;
    }
  }

  .bookDescription {
    padding: 5%;
    display: flex;
    height: 50%;
    flex-direction: column;
    row-gap: 1vh;
    align-items: center;
    overflow-y: auto;
    .bookTitle {
      font-size: 1.5rem;
      text-align: center;
    }
    .bookSummary {
      white-space: pre-line;
      text-align: justify;
    }
  }
}
</style>
