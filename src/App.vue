<template>
<div class="container">
  <h1 class="text-center">Il nostro primo esercizio in VUE</h1>
  <div class="row">
    <div v-for="announcement in announcements" class="col-12 col-md-4">
        <h2 class="text-center">{{announcement.name}}</h2>
        <button class="btn btn-outline-info d-block mx-auto">{{announcement.category}}</button>
        <h3 class="text-center">{{announcement.price}}&euro;</h3>
        <button @click="salvaProdotto(announcement)" class="btn btn-info d-block mx-auto" data-bs-toggle="modal" data-bs-target="#exampleModal">Dettagli</button>


    
    </div>
  </div>
</div>

<Detail :announcement="announcement" />

</template>

<script>
import Detail from './components/Detail.vue'
export default {
  name: 'App',
  components:{Detail},  // E' un set, ovvero non accetta duplicazioni

  data(){
    return {
      announcements: [
        {id:1, name: 'Armadio', category: 'Arredamento', price:2000},
        {id:2, name: 'Quadro', category: 'Arte', price:1000},
        {id:3, name: 'Automobile', category: 'Motori', price:200000}

        ],
        announcement : {}
    }
  },
  methods:{
    salvaProdotto(prodotto){
      this.announcement = prodotto
    }
  }

}
</script>

<style>

</style>
