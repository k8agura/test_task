<template>
  <div class="row justify-content-between mb-5">
      <catalog-item v-for="travel in travels"
                    :key="travel.id"
                    :travel="travel"
      />
  </div>
</template>
<script>
import CatalogItem from "@/components/CatalogItem";
export default {
  name: "Catalog",
  components: {CatalogItem},
  props: {
    travels: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {

    }
  },
}
</script>

<style scoped>
</style>