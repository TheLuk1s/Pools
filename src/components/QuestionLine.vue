<template>
  <b-row class="mb-3">
    <b-col cols="12" md="6">
      <b-form-input placeholder="Klausimas"></b-form-input>
    </b-col>
    <b-col cols="12" md="6">
      <b-form-select>
        <b-form-select-option value="1">Tekstas</b-form-select-option>
        <b-form-select-option value="4">Taip / Ne</b-form-select-option>
      </b-form-select>
    </b-col>
  </b-row>
</template>

<script>
export default {
  name: "QuestionLine",
};
</script>

<style scoped lang="scss">
</style>