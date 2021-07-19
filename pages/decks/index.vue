<template>
  <div>
    <div class="ct">
      <div class="d_flex justify_content_between my_3">
        <h3>List of your decks:</h3>
        <button class="btn btn_success" @click.prevent="openModal">
          Create a Deck
        </button>
      </div>

      <ul class="decks-list">
        <deck-list
          v-for="deck in decks"
          :id="deck._id"
          :key="deck._id"
          :name="deck.name"
          :thumbnail="deck.thumbnail"
          :description="deck.thumbnail"
        />
      </ul>
    </div>

    <!-- Modal -->
    <v-modal name="CreateDeckModal">
      <div class="modal_body">
        <h2>Create a new Deck</h2>
        <form action="">
          <div class="form_group">
            <label for="">Name:</label>
            <input
              class="form_control"
              type="text"
              placeholder="Please enter name"
            />
          </div>

          <div class="form_group">
            <label for="">Description:</label>
            <textarea
              class="form_control"
              placeholder="Please enter description"
            />
          </div>

          <div class="form_group">
            <label for="">Thumbnail:</label>
            <input type="file" />
            <div class="preview"></div>
          </div>

          <div class="form_group d_flex justify_content_end">
            <button class="btn btn_danger" @click.prevent="closeModal">
              Close
            </button>

            <button class="btn btn_success ml_3" @click.prevent="createDeck">
              Create
            </button>
          </div>
        </form>
      </div>
    </v-modal>
  </div>
</template>

<script>
import DeckList from '@/components/Decks/DeckList.vue'

export default {
  components: {
    DeckList,
  },
  data() {
    return {
      decks: [
        {
          _id: 1,
          name: 'Learn English',
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          thumbnail:
            'https://wallpaperbat.com/img/566655-english-class-wallpaper-png-free-english-class-wallpaperpng-transparent-image.png',
        },
        {
          _id: 2,
          name: 'Learn Chinese',
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          thumbnail:
            'https://wallpaperbat.com/img/566655-english-class-wallpaper-png-free-english-class-wallpaperpng-transparent-image.png',
        },
        {
          _id: 3,
          name: 'Learn Japanese',
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          thumbnail:
            'https://wallpaperbat.com/img/566655-english-class-wallpaper-png-free-english-class-wallpaperpng-transparent-image.png',
        },
      ],
    }
  },
  methods: {
    // showDeck() {
    //   this.$router.push(`/decks/${this.deckID}`)
    // },
    openModal() {
      this.$modal.open({ name: 'CreateDeckModal' })
    },
    closeModal() {
      this.$modal.close({ name: 'CreateDeckModal' })
    },
  },
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

.modal_body {
  background-color: #fff;
  padding: 1rem;
}
</style>
