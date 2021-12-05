<template>
  <div>
    <b-row class="mb-3" v-if="InputType === 1">
      <!-- Input -->
      <b-form-input
        :state="invalidAnswer"
        v-model="inputValue"
        :placeholder="Name"
      ></b-form-input>
    </b-row>
    <b-row class="mb-3" v-if="InputType === 4">
      <!-- Yes / No Radio as buttons -->
      <b-col v-bind:class="{ active: invalidAnswer } + ' pl-1 label'">{{
        Name
      }}</b-col>
      <b-col class="pr-0 d-flex justify-content-right">
        <b-form-group>
          <b-form-radio-group v-model="inputValue" buttons>
            <b-form-radio value="yes">Taip</b-form-radio>
            <b-form-radio value="no">Ne</b-form-radio>
          </b-form-radio-group>
        </b-form-group>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: "AnswerLine",

  props: {
    ID: {
      type: Number,
      required: true,
    },
    IDPoll: {
      type: Number,
    },
    Name: {
      type: String,
      required: true,
    },
    InputType: {
      type: Number,
    },
    InputValues: {
      type: String,
    },
  },

  data() {
    return {
      inputValue: "",
      invalidAnswer: null,
    };
  },

  methods: {
    getAnswer() {
      if (this.inputValue == "") {
        this.invalidAnswer = false;
        return false;
      } else {
        this.invalidAnswer = null;
        return [this.ID, this.inputValue];
      }
    },
  },
};
</script>

<style scoped lang="scss">
.label {
  color: rgb(108, 117, 125);
}

.justify-content-right {
  justify-content: right;
}
</style>