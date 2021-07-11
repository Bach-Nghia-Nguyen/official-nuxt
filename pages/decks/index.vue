<template>
  <div>
    <div class="ct">
      <h3>List of your decks:</h3>
      <ul class="decks-list">
        <li>
          <nuxt-link class="deck" to="/decks/1">
            <div class="card deck-card">
              <img
                src="https://wallpaperbat.com/img/566655-english-class-wallpaper-png-free-english-class-wallpaperpng-transparent-image.png"
                alt="thumbnail card"
              />
              <div class="card_body">
                <h3>Title card</h3>
                <p>Description card</p>
              </div>
            </div>
          </nuxt-link>
        </li>

        <li>
          <nuxt-link class="deck" to="/decks/2">
            <div class="card deck-card">
              <img
                src="https://wallpaperbat.com/img/566655-english-class-wallpaper-png-free-english-class-wallpaperpng-transparent-image.png"
                alt="thumbnail card"
              />
              <div class="card_body">
                <h3>Title card</h3>
                <p>Description card</p>
              </div>
            </div>
          </nuxt-link>
        </li>

        <li>
          <nuxt-link class="deck" to="/decks/3">
            <div class="card deck-card">
              <img
                src="https://wallpaperbat.com/img/566655-english-class-wallpaper-png-free-english-class-wallpaperpng-transparent-image.png"
                alt="thumbnail card"
              />
              <div class="card_body">
                <h3>Title card</h3>
                <p>Description card</p>
              </div>
            </div>
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  // methods: {
  //   showDeck() {
  //     this.$router.push(`/decks/${this.deckID}`)
  //   },
  // },
}
</script>

<style lang="scss">
.decks-list {
  li {
    list-style: none;
    margin-bottom: 1rem;
    &:last-child {
      margin-bottom: 0;
    }

    .deck {
      display: block;
    }
  }

  .deck-card {
    display: flex;
    flex-direction: row;
    height: 250px;
    img {
      width: 250px;
      height: auto;
    }
  }
}
</style>
