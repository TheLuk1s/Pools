<template>
  <b-container>
    <!-- Headline wrapper -->
    <b-row class="my-3">
      <b-col class="text-center"><h2>Kurti klausimyną</h2></b-col>
    </b-row>

    <!-- Questions wrapper -->
    <QuestionLine
      ref="questions"
      :key="question"
      v-for="question in questions"
    />

    <!-- Button wrapper -->
    <div class="button--poll-save">
      <b-button pill variant="info" size="lg" v-on:click="savePoll"
        ><b-icon icon="check" scale="1" aria-hidden="true"></b-icon
      ></b-button>
    </div>
    <div class="button--question-add">
      <b-button pill variant="success" size="lg" v-on:click="questions++"
        >+</b-button
      >
    </div>
  </b-container>
</template>

<script>
// Components
import QuestionLine from "../components/QuestionLine";

// Essentials
// import axios from "axios";

// Defaults
export default {
  name: "CreatePool",
  components: {
    QuestionLine,
  },
  data() {
    return {
      questions: 1,
    };
  },
  methods: {
    savePoll() {
      let questions = [];

      this.$refs.questions.forEach((element) => {
        if (typeof element.getQuestion() != "undefined") {
          questions.push(element.getQuestion());
        }
      });

      console.log(questions);
    },
  },
};
</script>

<style scoped lang="scss">
.button--question-add {
  position: fixed;
  right: 0;
  bottom: 0;
  margin: 30px;
}

.button--poll-save {
  position: fixed;
  left: 0;
  bottom: 0;
  margin: 30px;

  button {
    padding: 8px 10px;
  }
}
</style>