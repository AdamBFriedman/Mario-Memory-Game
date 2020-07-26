<template>
  <div id="app">
    <div id="game"></div>
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
let cardsArray = [
  {
    name: "shell",
    img: "img/blueshell.png",
  },
  {
    name: "star",
    img: "img/star.png",
  },
  {
    name: "bobomb",
    img: "img/bobomb.png",
  },
  {
    name: "mario",
    img: "img/mario.png",
  },
  {
    name: "luigi",
    img: "img/luigi.png",
  },
  {
    name: "peach",
    img: "img/peach.png",
  },
  {
    name: "1up",
    img: "img/1up.png",
  },
  {
    name: "mushroom",
    img: "img/mushroom.png",
  },
  {
    name: "thwomp",
    img: "img/thwomp.png",
  },
  {
    name: "bulletbill",
    img: "img/bulletbill.png",
  },
  {
    name: "coin",
    img: "img/coin.png",
  },
  {
    name: "goomba",
    img: "img/goomba.png",
  },
];

let gameGrid = cardsArray.concat(cardsArray).sort(function () {
  return 0.5 - Math.random();
});

let firstGuess = "";
let secondGuess = "";
let count = 0;
let previousTarget = null;
let delay = 1200;

let game = document.getElementById("game");
let grid = document.createElement("section");
grid.setAttribute("class", "grid");
game.appendChild(grid);

gameGrid.forEach(function (item) {
  let name = item.name,
    img = item.img;

  let card = document.createElement("div");
  card.classList.add("card");
  card.dataset.name = name;

  let front = document.createElement("div");
  front.classList.add("front");

  let back = document.createElement("div");
  back.classList.add("back");
  back.style.backgroundImage = "url(" + img + ")";

  grid.appendChild(card);
  card.appendChild(front);
  card.appendChild(back);
});

let match = function match() {
  let selected = document.querySelectorAll(".selected");
  selected.forEach(function (card) {
    card.classList.add("match");
  });
};

export default {
  name: "App",
  components: {
    // HelloWorld
  },
};
</script>

<style>
#app {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  text-align: center;
}
</style>
