<template>
  <div>
    <div>
      <button class="yes" @click="foodora" v-if="buttonType === 'Ja'">
        Ja
      </button>
      <button class="no" @click="visaMeddelande" v-if="buttonType === 'Nej'">
        Nej
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    buttonType: {
      type: String,
      required: true,
      validator: (value) => {
        return ["Ja", "Nej"].includes(value);
      },
    },
  },
  methods: {
    foodora() {
      if (this.buttonType === "Ja") {
        window.location.href =
          "https://www.foodora.se/?gclid=Cj0KCQiAorKfBhC0ARIsAHDzslszgiwKiEC7xdE4cpMFxH_HBscH-5tCwY28MuzP9tSrZVZ_cXw-OPIaApzcEALw_wcB";
      }
    },
    visaMeddelande() {
      if (this.buttonType === "Nej") {
        alert("Bra jobbat Richard!");
      }
    },
  },
};
</script>
<style scoped>
.yes {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-family: "Montserrat", sans-serif;
  border-radius: 9%;
  background-color: #3b443b;
  color: white;
  padding: 12px 24px;
  border: none;
  border-radius: 4px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}
.no {
  position: absolute;
  top: 50%;
  left: 46%;
  transform: translate(-50%, -50%);
  font-family: "Montserrat", sans-serif;
  border-radius: 9%;
  background-color: #3b443b;
  color: white;
  padding: 12px 24px;
  border: none;
  border-radius: 4px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}
</style>
