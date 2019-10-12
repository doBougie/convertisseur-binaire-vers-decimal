<template>
  <div id="app">
    Nombre en binaire
    <br>
    {{bin()}}
    <br>
    <div>
      <button @click="invertBin(0)">{{nbBinaires[0]}}</button>
      <button @click="invertBin(1)">{{nbBinaires[1]}}</button>
      <button @click="invertBin(2)">{{nbBinaires[2]}}</button>
      <button @click="invertBin(3)">{{nbBinaires[3]}}</button>
      <button @click="invertBin(4)">{{nbBinaires[4]}}</button>
      <button @click="invertBin(5)">{{nbBinaires[5]}}</button>
      <button @click="invertBin(6)">{{nbBinaires[6]}}</button>
      <button @click="invertBin(7)">{{nbBinaires[7]}}</button>
    </div>
    <br>
    En décimale
    <br>
    {{bin_to_dec(bin())}}

  </div>
</template>

<script>


export default {
  name: 'app',
  data() {
    return {
      nbBinaires: [0, 0, 0, 0, 0, 0, 0, 0],

    };
  },
  methods: {
    invertBin(id) {
      if (this.nbBinaires[id] === 0) {
        console.log('test');
        this.nbBinaires[id] = 1;
      } else {
        console.log('test2');
        this.nbBinaires[id] = 0;
      }
      this.$forceUpdate();
    },
    bin() {
      let bin = '';
      this.nbBinaires.forEach((nb) => {
        bin += nb;
      });
      return bin;
    },
    bin_to_dec(bstr) {
      return parseInt((`${bstr}`)
        .replace(/[^01]/gi, ''), 2);
    },
  },
};
</script>

<style lang="scss">
#app{
  font-size: 50px;
}
</style>
