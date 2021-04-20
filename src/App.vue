<template>
  <Nav />
  <div class="row m-lg-5 m-3">
    <div class="col-lg-8 mt-2 mt-md-0">
      <div v-if="!showResult">
        <Workoutsvg />
      </div>
      <div class="text-center" v-else>
        <h1>Your BMI is {{ bmiValue }}</h1>
        <Resultsvg
          v-bind:meters="heightM"
          v-bind:feet="heightFeet"
          v-bind:inches="heightInches"
          v-bind:kilograms="weightKg"
          v-bind:pounds="weightLbs"
        />
      </div>
    </div>
    <div class="col-lg-4 mb-md-0 mt-md-0 mt-5 mb-5">
      <Form @bmiValue="processBmi" />
    </div>
  </div>
</template>

<script>
import Form from "./components/bmi-form.vue";
import Nav from "./components/nav-bar.vue";
import Workoutsvg from "./components/svgs/workout-svg.vue";
import Resultsvg from "./components/svgs/bmi-chart-svg";

export default {
  data() {
    return {
      bmiValue: 0,
      showResult: false,
      weightKg: 0,
      weightLbs: 0,
      heightM: 0,
      heightInches: 0,
      heightFeet: 0,
    };
  },
  components: { Form, Nav, Workoutsvg, Resultsvg },
  methods: {
    processBmi(e) {
      this.bmiValue = e["bmi"];
      this.weightKg = e["kgs"];
      this.weightLbs = e["pounds"];
      this.heightM = e["meters"];
      this.heightInches = e["inches"];
      this.heightFeet = e["feet"];

      console.log(this);
      this.showResult = true;
    },
  },
};
</script>

<style>
/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type="number"] {
  -moz-appearance: textfield;
}
</style>
