<template>
  <!-- Pools -->
  <b-container class="mt-5">
    <b-row align-h="center">
      <b-col
        v-for="pool in pools"
        :key="pool.ID"
        class="mx-auto"
        cols="12"
        md="6"
        lg="4"
      >
        <PoolCard
          :ID="pool.ID"
          :Name="pool.Name"
          :Rating="
            pool.Rating
              ? parseFloat(pool.Rating).toFixed(2)
              : parseFloat(0).toFixed(2)
          "
          :IsPublic="pool.IsPublic"
        />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
// Components
import PoolCard from "../components/PoolCard";

// Essentials
import axios from "axios";

export default {
  name: "Home",
  components: {
    PoolCard,
  },
  data() {
    this.getAllPools();

    return {
      pools: null,
    };
  },
  methods: {
    getAllPools() {
      const pools = axios
        .get("https://polls.modsol.net/public/api/poll")
        .then((response) => {
          if (response.status == 200) {
            this.pools = response.data;
          }
        });
    },
  },
};
</script>

<style>
</style>
