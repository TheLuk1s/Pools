<template>
  <div id="app">
    <Navbar name="Klausimynas" />

    <!-- UserModals -->
    <b-modal id="modalLogin" title="Prisijungimas" hide-footer>
      <Login />
    </b-modal>
    <b-modal id="modalRegister" title="Registracija" hide-footer>
      <Register />
    </b-modal>

    <!-- Router -->
    <router-view></router-view>
  </div>
</template>

<script>
// Components
import Navbar from "./components/Navbar";
import Login from "./components/User/Login";
import Register from "./components/User/Register";

// Defaults
export default {
  name: "App",
  components: {
    Navbar,
    Login,
    Register,
  },
};
</script>