<template>
    <div class="row justify-content-center" style="padding-top: 10vh;">
  <div v-for="item in Pokeresp" class="card col-sm-4" style="width: 18rem;">
    <img :src="item.bild" class="card-img-top" :alt="item.name">
    <div class="card-body">
      <h5 class="card-title">{{item.name}}</h5>
      <p class="card-text">{{ item.description }}</p>
      <p>{{ item.pris }}kr</p>
      <button class="btn btn-primary" @click="köp(item)">Köp</button>
    </div>
  </div>
</div>
<p v-if="totalPrice !== 50">Din varukorgs totala pris: {{ totalPrice }}</p>
<p v-if="totalPrice < 1000 && totalPrice !== 50">Frakt kostnad 50kr (Du uppnår grattis frakt om {{ this.gratisFrakt }}kr)</p>
<p v-if="totalPrice > 1000">Du har uppnått grattis frakt</p>
</template>

<script>
    import Pokedata from '../assets/Poke.json'
    export default {

        data() {
    return {
      Pokeresp: Pokedata,
      totalPrice: 50,
      frakt: 50,
      gratisFrakt: 1000
    };
  },methods: {
  köp(item) {
if(this.totalPrice > 1000 && this.frakt === 50){
    this.totalPrice += item.pris;
    this.totalPrice -50
    this.frakt -50
}
else{
    this.totalPrice += item.pris;
    this.gratisFrakt = 1050 - this.totalPrice
}


  },
}
}
</script>

<style>
    @media (min-width: 1024px) {
        .about {
            min-height: 100vh;
            display: flex;
            align-items: center;
        }
    }
</style>
