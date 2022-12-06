<template>
  <div class="px-3 my-4">
    <label for="carBrands" class="text-gray-400">Title</label>
  </div>
  <div>
    <input
      type="text"
      class="text-sm px-4 py-2 w-full rounded-md bg-gray-600 text-white outline-none"
      placeholder="Car Name e.g. father's car"
    />
  </div>

  <div class="px-3 my-4">
    <label for="carBrands" class="text-gray-400">Select your car brand</label>
  </div>
  <div>
    <select
      class="text-sm px-2 py-2 w-full rounded-md bg-gray-600 text-white outline-none"
      v-model="carBrand"
      name="carsBrands"
      @change="hesapla()"
    >
      <option v-for="(car, key) in cars" :value="key">{{ car.brand }}</option>
    </select>
  </div>

  <div class="px-3 my-4">
    <label for="carBrands" class="text-gray-400">Select your car model</label>
  </div>
  <div>
    <select
      class="text-sm px-2 py-2 w-full rounded-md bg-gray-600 text-white outline-none"
      v-model="carModel"
      name="carsBrands"
    >
      <option v-for="models in brand" :value="models.models">{{ models }}</option>
    </select>
  </div>

  <div class="px-3 my-4">
    <label for="carBrands" class="text-gray-400">Plate Number</label>
  </div>
  <div>
    <input
      type="text"
      class="text-sm px-4 py-2 w-full rounded-md bg-gray-600 text-white outline-none"
      placeholder="Plate Number"
    />
  </div>

  <button
    @click="publishMessageActive = !publishMessageActive"
    class="bg-purple-600 text-white my-9 w-full rounded-md px-2 py-1.5"
  >
    Save
  </button>

  <div
    v-if="publishMessageActive"
    :class="[
      messages[publishStatus].class,
      publishMessageActive ? 'vov flash faster' : '',
    ]"
    class="text-white px-4 py-2 rounded-md text-sm border absolute  bottom-32 grid place-items-center z-999  "
  >
    <i :class="messages[publishStatus].icon" class="mr-3"></i>
    {{ messages[publishStatus].MessageText }}
  </div>
</template>
<style scoped>
.z-999{
z-index: 999;
width: 100%;


}
</style>
<script>
import carlist from "../../assets/carlist.json";
export default {
  methods: {
    hesapla() {
      console.log(this.carBrand),
        (this.brand = this.cars[this.carBrand].models),
        console.log(this.brand);
    },
  },

  data() {
    return {
      cars: carlist,

      carBrand: "",
      carModel: "",
      brand: [],
      publishMessageActive: true,
      publishStatus: 1,
      messages: [
        {
          0: "SuccessMessage",
          MessageText: "Successfully Saved",
          icon: "far fa-check",
          class: "bg-green-600/30 border-green-500",
        },
        {
          1: "FailureMessage",
          MessageText: "An error has occurred",
          icon: "far fa-triangle-exclamation",
          class: "bg-red-600/30 border-red-500",
        },
      ],
    };
  },
};
</script>
