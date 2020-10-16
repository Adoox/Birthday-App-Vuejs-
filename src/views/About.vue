<template>
  <div id="app">
    <div id="desktop-view">
      <div id="alert-box">
        <h2>Aplikacija nije dostupna na desktop i laptop računalima!</h2>
      </div>
    </div>
    <div id="mobile-view">
      <h4>Birthday Memory Game</h4>
      <div id="cards-flex">
        <div
          id="card"
          v-for="card in cards"
          :key="card.id"
          @click="click(card)"
        >
          <img v-bind:src="card.blank_img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import swal from "sweetalert";
export default {
  name: "App",
  data() {
    return {
      pobjeda: false,
      cards: [
        {
          id: 0,
          card_id: 1,
          blank_img:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          blank_img_2:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          flip_img: require("../../images/img1.jpg"),
        },
        {
          id: 1,
          card_id: 3,
          blank_img:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          blank_img_2:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          flip_img: require("../../images/img3.jpg"),
        },
        {
          id: 2,
          card_id: 2,
          blank_img:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          blank_img_2:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          flip_img: require("../../images/img2.jpg"),
        },
        {
          id: 3,
          card_id: 2,
          blank_img:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          blank_img_2:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          flip_img: require("../../images/img2.jpg"),
        },
        {
          id: 4,
          card_id: 1,
          blank_img:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          blank_img_2:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",

          flip_img: require("../../images/img1.jpg"),
        },
        {
          id: 5,
          card_id: 3,
          blank_img:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          blank_img_2:
            " https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Question_Mark.svg/1200px-Question_Mark.svg.png",
          flip_img: require("../../images/img3.jpg"),
        },
      ],

      cards_chosen: [],
      card_chosen_id: [],
      cards_won: [],
    };
  },
  methods: {
    check() {
      let card_one = this.cards_chosen[0];
      let card_two = this.cards_chosen[1];
      if (this.card_chosen_id[0] === this.card_chosen_id[1]) {
        this.cards[card_one].flip_img = " ";
        this.cards[card_one].blank_img = " ";
        this.cards[card_two].flip_img = " ";
        this.cards[card_two].blank_img = " ";
        this.cards_chosen = [];
        this.card_chosen_id = [];
        this.cards_won.push(this.cards_chosen);
      } else {
        this.cards[card_one].blank_img = this.cards[card_one].blank_img_2;
        this.cards[card_two].blank_img = this.cards[card_two].blank_img_2;
        this.cards_chosen = [];
        this.card_chosen_id = [];
      }

      if (this.cards_won.length == this.cards.length / 2) {
        this.pobjeda = true;
        swal("Your text goes here").then(() => {
          swal(`Your message goes here!`);
        });
      }
    },
    click(e) {
      let x = e.id;
      console.log(x);
      this.cards_chosen.push(x);
      this.card_chosen_id.push(e.card_id);
      for (let i = 0; i < this.cards.length; i++) {
        if (this.cards[i].id == x) {
          this.cards[i].blank_img = this.cards[i].flip_img;
        }
      }

      console.log("Duzina:" + this.cards_chosen.length);
      if (this.cards_chosen.length === 2) {
        setTimeout(this.check, 700);
      }
    },
  },
  components: {},
};
</script>

<style >
#app h4 {
  padding: 10px;
}

#card {
  width: 45%;
  height: 170px;
  background-color: rgb(211, 211, 211);
}

#card img {
  width: 100%;
  height: 100%;
}

#cards-flex {
  margin: 0 auto;
  width: 90%;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: space-between;
  height: 90vh;
}

@media only screen and (max-width: 430px) {
  #desktop-view {
    display: none;
  }
}

@media only screen and (min-width: 430px) and (max-width: 960px) {
  #desktop-view {
    display: none;
  }
}
@media only screen and (min-width: 961px) {
  #mobile-view {
    display: none;
  }
}
</style>

