<template>
  <section>
    <div class="r">
      <div class="ct text_center">
        <h3>Deck #{{ $route.params.id }}: Learn English by Sky Albert</h3>
        <div class="tools">
          <button class="btn btn_success">Start now</button>
          <button class="btn btn_primary" @click.prevent="openModal">
            Create a card
          </button>
        </div>

        <hr class="divide" />

        <div class="r">
          <card-list
            v-for="card in cards"
            :id="card._id"
            :key="card._id"
            :picture="card.picture"
            :keyword="card.keyword"
          />
        </div>
      </div>
    </div>

    <!-- Modal -->
    <v-modal name="CreateCardModal">
      <div class="modal_body">
        <h2>Create a new Card</h2>
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
  </section>
</template>

<script>
import CardList from '@/components/Cards/CardList.vue'
export default {
  components: { CardList },
  validate({ params }) {
    // check the validity of param id
    return /^[0-9]$/.test(params.id)
  },
  data() {
    return {
      cards: [
        {
          _id: 1,
          picture:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Road_in_Norway.jpg/1200px-Road_in_Norway.jpg',
          keyword: 'Road',
        },
        {
          _id: 2,
          picture:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Road_in_Norway.jpg/1200px-Road_in_Norway.jpg',
          keyword: 'Road',
        },
        {
          _id: 3,
          picture:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Road_in_Norway.jpg/1200px-Road_in_Norway.jpg',
          keyword: 'Road',
        },
        {
          _id: 4,
          picture:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Road_in_Norway.jpg/1200px-Road_in_Norway.jpg',
          keyword: 'Road',
        },
        {
          _id: 5,
          picture:
            'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Road_in_Norway.jpg/1200px-Road_in_Norway.jpg',
          keyword: 'Road',
        },
      ],
    }
  },

  methods: {
    openModal() {
      this.$modal.open({ name: 'CreateCardModal' })
    },
    closeModal() {
      this.$modal.close({ name: 'CreateCardModal' })
    },
  },
}
</script>

<style lang="scss">
section {
  padding-top: 3rem;
  .card {
    padding: 1rem;
    img {
      width: 60%;
    }
  }
  .divide {
    margin: 2rem 0;
  }
}

.modal_body {
  background-color: #fff;
  padding: 1rem;
}
</style>
