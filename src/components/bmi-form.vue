<template>
  <div class="container form-container pt-md-5">
    <form @submit.prevent="calculateBMI">
      <div class="form-row">
        <div class="form-group col-6">
          <label>Height</label>
          <input
            v-model="feet"
            class="form-control"
            type="number"
            placeholder="Feet"
            min="1"
          />
        </div>
        <div class="form-group col-6 no-label">
          <input
            v-model="inches"
            class="form-control"
            type="number"
            min="0"
            max="12"
            placeholder="Inches"
          />
        </div>
      </div>
      <div class="form-row">
        <div class="form-group col-md-8">
          <label for="inputAddress">Weight</label>
          <input
            min="1"
            type="number"
            class="form-control"
            v-model="weight"
            :placeholder="'Weight (' + [[unit]] + ')'"
          />
        </div>
        <div class="form-group col-md-4">
          <label>Unit</label>
          <select v-model="unit" class="form-control">
            <option selected>Kg</option>
            <option>Lbs</option>
          </select>
        </div>
      </div>
      <button
        type="submit"
        :disabled="buttonController()"
        class="btn btn-primary btn-lg"
      >
        Calculate
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      feet: "",
      inches: "",
      weight: "",
      unit: "Kg",
    };
  },
  methods: {
    buttonController() {
      if (this.feet != "" && this.inches != "" && this.weight != "") {
        return false;
      }
      return true;
    },
    resetForm() {
      (this.feet = ""), (this.inches = ""), (this.weight = "");
    },
    calculateBMI() {
      //form data
      let feet = parseInt(this.feet);
      let inches = parseInt(this.inches);
      let weight = parseInt(this.weight);

      //main logic
      let height = (feet + inches / 12) / 3.2808;

      if (this.unit === "Lbs") {
        //lbs to kg
        weight = weight / 2.2046;
      }

      let bmi = Number(weight / height ** 2).toFixed(1);
      this.$emit("bmiValue", {
        bmi: bmi,
        pounds: Number(weight * 2.2046).toFixed(2),
        kgs: weight,
        feet: feet,
        inches: inches,
        meters: Number(height).toFixed(2),
      });
      this.resetForm();
    },
  },
};
</script>

<style>
.no-label {
  margin-top: 2rem;
}
.form-container {
  height: 100%;
  padding: 2rem;
  border-radius: 15px;
  max-width: 500px;
  /* min-width: 300px; */
  background-color: #eee;
}
</style>