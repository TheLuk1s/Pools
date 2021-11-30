<template>
  <div>
    <b-form class="d-flex justify-content-between" inline>
      <b-form-input class="my-3 pr-4" placeholder="Vardas"></b-form-input>
      <b-form-input class="my-3 pr-5" placeholder="Pavardė"></b-form-input>
    </b-form>
    <b-form>
      <b-input-group prepend="@">
        <b-form-input placeholder="El. pašto adresas"></b-form-input>
      </b-input-group>

      <b-form-input
        placeholder="Slaptažodis"
        type="password"
        class="my-3"
      ></b-form-input>

      <b-button squared variant="outline-secondary float-right"
        >Registruotis</b-button
      >
    </b-form>
  </div>
</template>

<script>
export default {
  name: "Register",
  props: {},
};
</script>

<style scoped lang="scss">
</style>