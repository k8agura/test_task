<template>
  <div class="app bg-dark">
    <Header></Header>
    <div class="container mt-2 d-flex flex-column bg-light">
      <div class="container row mt-4">
        <div class="col-4"><Filters :options="options" v-model="value"/></div>
        <div class="col-8">
          <input-search v-model="input"></input-search>
          <Catalog :travels="filteredCity"/>
        </div>
      </div>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Catalog from "@/components/Catalog";
import CatalogItem from "@/components/CatalogItem";
import Footer from "@/components/Footer";
import Filters from "@/components/Filters";
import inputSearch from "@/components/inputSearch";
export default {
  name: "App",
  components: { Catalog, Header, CatalogItem, Footer,Filters,inputSearch},
  data(){
    return{
      travels: [
        {
          id: 0,
          photo: "Sochi.jpg",
          country: "Россия",
          city: "Сочи",
          price: "15000"
        },
        {
          id: 1,
          photo: "Praga.jpg",
          country: "Чехия",
          city: "Прага",
          price: "25000"
        },
        {
          id: 2,
          photo: "Gamburg.jpg",
          country: "Германия",
          city: "Гамбург",
          price: "45000"
        },
        {
          id: 3,
          photo: "Moscow.jpg",
          country: "Россия",
          city: "Москва",
          price: "10000"
        }
      ],
      options: [
        {name:"Все", value:"on"}, /*так то здесь должен быть null*/
        {name:"Россия", value:"Россия"},
        {name:"Германия", value:"Германия"},
        {name:"Чехия", value:"Чехия"},
      ],
      value: 'on',
      input:'',
    }
  },
computed: {
  filteredCity() {
    return this.filteredCountry.filter(travel => {
      return travel.city.toLowerCase().indexOf(this.input.toLowerCase()) > -1
    })
  },
  filteredCountry() {
    if(this.value != "on")
      return this.travels.filter(travel => {
        return travel.country.indexOf(this.value) > -1
      })
    else
      return this.travels
  }
}
}
</script>

<style >
::-webkit-scrollbar {
  width: 0;
}
</style>