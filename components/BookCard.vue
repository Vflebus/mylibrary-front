<template>
  <div class="card">
    <section class="imgContainer">
      <img
        src="https://imagine.bayard.io/unsafe/560x0/bayard-static/edition/couvertures/9791036313691/9791036313691.jpg"
        alt=""
      />
    </section>
    <section class="bookDescription">
      <h3 class="bookTitle">Eragon</h3>
      <p class="bookSummary">
        Voilà bien longtemps que le mal règne dans l'Empire de l'Alagaësia... Et
        puis, un jour, le jeune Eragon découvre au cœur de la forêt une
        magnifique pierre bleue, étrangement lisse. Fasciné et effrayé, il
        l'emporte à Carvahall, le village où il vit très simplement avec son
        oncle et son cousin. Il n'imagine pas alors qu'il s'agit d'un veuf, et
        qu'un dragon, porteur d'un héritage ancestral, aussi vieux que l'Empire
        lui-même, va en éclore... Très vite, la vie d'Eragon est bouleversée.
        Contraint de quitter les siens, il s'engage dans une quête qui le mènera
        aux confins de l'Alagaësia. Armé de son épée et guidé par les conseils
        de Brom, le vieux conteur, Eragon va devoir affronter, avec son jeune
        dragon, les terribles ennemis envoyés par le roi dont la malveillance
        démoniaque ne connaît aucune limite. Eragon n'a que quinze ans, mais le
        destin de l'Empire est désormais entre ses mains ! Un livre hors du
        commun, digne de J.R.R. Tolkien, écrit par un très jeune écrivain qui,
        avec le premier roman de cette trilogie " l'Héritage ", est d'ores et
        déjà entré au panthéon des grands auteurs de la littérature de Fantasy !
      </p>
      <p>Note: 4/5</p>
      <p>Paru le 03/05/1996</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'BookCard',
}
</script>

<style lang="scss" scoped>
.card {
  width: 80%;
  height: 70vh;
  border-radius: 30px;
  overflow: hidden;
  border: 1px white solid;
  overflow-y: auto;
  .imgContainer {
    width: 100%;
    height: 40%;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .bookDescription {
    padding: 5%;
    display: flex;
    flex-direction: column;
    row-gap: 1vh;
    align-items: center;
    .bookTitle {
        font-size: 1.5rem;
    }
  }
}
</style>
