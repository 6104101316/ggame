<template>
  <div>
    <p>
      HP Player {{randomNO(1,3)}}
      {{player[randomNo(1,3)-1].name}}
    </p>
    +image
    <hr />
    name = {{aPlayer.name}}
    hp = {{aPlayer.hp}}
    image = {{aPlayer.image}}
    <hr />
    <p>
      HP Monster {{randomDamageNo(1,3)}}
      {{monster[randomDamageNo(1,3)-1].name}}
    </p>
    +image
    <hr />
    name = {aMonster.name}}
    hp = {{aMonster.hp}}
    image = {{aMonster.image}}
    <hr />

    <button @click="start()">Start</button>
    <button @click="attack()">Attack</button>
    <button>Spacial Attack</button>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      aPlayer: { name: "", hp: "" },
      aMonster: { name: "", hp: "" },
      player: [
        { name: "Iron Man", hp: 120 },
        { name: "Doraemon", hp: 120 },
        { name: "Skywalker", hp: 100 },
 
      ],
      monster: [
        { name: "Thanos", hp: 200 },
        { name: "Darth vader", hp: 190 },
        { name: "Cell ", hp: 180 },
      ],
    };
  },
  methods: {
    randomDamageNo: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start: function () {
      //random player
      this.aPlayer = this.player[this.randomDamageNo(0, 2) - 1];
      //random monster
      this.aMonster = this.monster[this.randomDamageNo(0, 2) - 1];
    },
    attack: function () {},
  },
};
</script>
<style lang="">
</style>