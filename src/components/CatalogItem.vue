<template>
  <div class="card text-center card-product mt-4" style="width: 17rem;">
    <div class="card-product__img">
      <img :src="require('@/assets/img/' + travel.photo)" class="card-img"/>
    </div>
    <div class="card-body">
      <h5 class="card-title">{{travel.country}}</h5>
      <p class="card-text ">Город: {{travel.city}}</p>
      <p class="card-text">Цена: {{travel.price}}руб.</p>
      <p><button type="button" class="btn btn-primary">Заказать</button></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "CatalogItem",
  props: {
    travel: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style>

</style>