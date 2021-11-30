<template>
  <div>
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
        >Prisijungti</b-button
      >
    </b-form>
  </div>
</template>

<script>
export default {
  name: "Login",
  props: {},
};
</script>

<style scoped lang="scss">
</style>