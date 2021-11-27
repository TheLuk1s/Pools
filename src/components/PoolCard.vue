<template>
  <div>
    <b-card
      :title="name"
      img-src="https://picsum.photos/600/300/?image=25"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem"
      class="mb-2"
    >
      <b-card-text>
        {{ description }}
      </b-card-text>

      <b-button :disabled="isPrivate" href="#" variant="primary"
        >Pildyti</b-button
      >
    </b-card>
  </div>
</template>

<script>
export default {
  name: "PoolCard",
  props: {
    name: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    isPrivate: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style scoped lang="scss">
</style>