<template>
  <div id="app">
    <Navbar name="Klausimynas" />
    <!-- Pools -->
    <b-container class="mt-5">
      <b-row align-h="center">
        <b-col
          v-for="pool in pools"
          :key="pool.name"
          class="mx-auto"
          cols="12"
          md="6"
          lg="4"
        >
          <PoolCard
            :name="pool.name"
            :description="pool.desciption"
            :isPrivate="pool.isPrivate"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
// Components
import Navbar from "./components/Navbar";
import PoolCard from "./components/PoolCard";

// Defaults
export default {
  name: "App",
  components: {
    Navbar,
    PoolCard,
  },
  data() {
    return {
      pools: [
        { name: "Foo", description: "ABC", isPrivate: false },
        { name: "Bar", description: "DDD", isPrivate: true },
      ],
    };
  },
};
</script>


