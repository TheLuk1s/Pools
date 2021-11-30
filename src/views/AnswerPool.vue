<template>
  <b-container>
    <!-- Headline wrapper -->
    <b-row class="my-3">
      <b-col class="text-center"><h2>Atsakyti klausimyną</h2></b-col>
    </b-row>

    <!-- Questions wrapper -->
    <AnswerLine
      ref="answers"
      v-bind="question"
      :key="question"
      v-for="question in questions"
      @answer="getAnswer"
    />

    <!-- Complete button wrapper -->
    <b-button v-on:click="fillAnswers" pill class="completeButton"
      ><b-icon icon="check" scale="2" aria-hidden="true"></b-icon
    ></b-button>
  </b-container>
</template>

<script>
// Components
import AnswerLine from "../components/AnswerLine";

// Essentials
import axios from "axios";

// Defaults
export default {
  name: "CreatePool",
  components: {
    AnswerLine,
  },
  data() {
    this.getAllQuestions();

    return {
      questions: null,
    };
  },
  methods: {
    getAllQuestions() {
      const questions = axios
        .get(
          "https://polls.modsol.net/public/api/poll/" +
            this.$route.params.pollID +
            "/option"
        )
        .then((response) => {
          console.log(response);
          if (response.status == 200) {
            this.questions = response.data;
          }
        });
    },

    fillAnswers() {
      let answers = [];

      this.$refs.answers.forEach((element) => {
        answers.push(element.getAnswer());
      });
    },
  },
};
</script>

<style scoped lang="scss">
.completeButton {
  position: fixed;
  right: 0;
  bottom: 0;
  margin: 30px;
  padding: 12px 15px;
}
</style>