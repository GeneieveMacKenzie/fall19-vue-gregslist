<template>
  <div class="houses">
    <div class="row">
      <house v-for="house in houses" :houseProp="house" :key="house._id" />
      <div class="col-12 pt-5">
        <CreateHouseModal />
        <button class="btn btn-primary" data-toggle="modal" data-target="#create-house-modal">List House</button>
      </div>
    </div>
  </div>
</template>


<script>
import House from "../components/House";

export default {
  name: "houses",
  data() {
    return {};
  },
  computed: {
    houses() {
      return this.$store.state.houses;
    }
  },
  mounted() {
    this.$store.dispatch("getHouses");
  },
  methods: {},
  components: { House }
};
</script>


<style scoped>
</style>