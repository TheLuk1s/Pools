<template>
  <div>
    <b-card
      :title="Name"
      img-src="https://picsum.photos/600/300/?image=25"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem"
      class="mb-2"
    >
      <b-card-text>
        <b-form-rating v-model="Rating" readonly></b-form-rating>
      </b-card-text>

      <b-button
        :disabled="IsPublic != 1"
        :href="'#/answerPool/' + ID"
        variant="primary"
        >Pildyti</b-button
      >
    </b-card>
  </div>
</template>

<script>
export default {
  name: "PoolCard",
  props: {
    ID: {
      type: Number,
      required: true,
    },
    IsPublic: {
      type: Number,
    },
    Name: {
      type: String,
      required: true,
    },
    Rating: {
      type: Number,
    },
  },
};
</script>

<style scoped lang="scss">
</style>