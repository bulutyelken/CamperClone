<template>
  <div class="erkek">
    <h1 id="baslık">Erkek Ayakkabıları</h1>
    <Filt />

    <v-row id="row">
      <v-col
        v-for="(item, index) in this.$store.state.itemserkek"
        :key="index"
        cols="3"
      >
        <v-img :src="item.image" aspect-ratio="1" class="grey lighten-2">
          <template v-slot:placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular
                indeterminate
                color="grey lighten-5"
              ></v-progress-circular>
            </v-row>
          </template>
        </v-img>
      </v-col>
    </v-row>
  </div>
</template>



<style scoped>
#baslık {
  margin-left: 680px;
  margin-top: 90px;
  font-size: 25px;
  font-weight: normal;
}
#row {
  margin-top: -700px;
}
</style>

<script>
import Filt from "../components/Filter.vue";
export default {
  beforeCreate() {
    this.$store.dispatch("fetchItemsForErkek");
  },
  name: "erkek",
  components: {
    Filt,
  },
};
</script>