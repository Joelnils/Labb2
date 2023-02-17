<template>
  <button class="knapp" @click="toggleVisibility">{{ buttonText }}</button>
  <div>
    <div v-if="visibility" class="card-deck">
      <div class="row">
        <div class="col-sm-3" v-for="drink in drinks" :key="drink.id">
          <div class="card">
            <img v-bind:src="drink.bild" class="card-img-top" alt="..." />
            <div class="card-body">
              <h5
                class="card-title"
                style="position: absolute; top: 10px; left: 10px"
              >
                {{ drink.drink }}
              </h5>
              <p
                class="card-text"
                style="position: absolute; top: 50px; left: 10px"
              >
                {{ drink.ingredienser }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      drinks: [],
      visibility: false,
      buttonText: "Visa Richard",
    };
  },
  methods: {
    toggleVisibility() {
      this.visibility = !this.visibility;
      this.buttonText = this.visibility ? "Göm Richard" : "Visa Richard";
    },
  },
  mounted() {
    fetch("./drink.json")
      .then((response) => response.json())
      .then((data) => {
        console.log(data);
        this.drinks = data;
      })
      .catch((error) => {
        console.error(error);
      });
  },
};
</script>
<style scoped>
.knapp {
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
.knapp:hover {
  background-color: #556068;
}
.knapp:active {
  background-color: #8598a5;
}
.card-deck {
  position: absolute;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.card {
  width: 250px;
  height: 150px;
}
.card-img-top {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.card-text {
  color: #ffffff;
  font-family: "Montserrat", sans-serif;
  font-size: medium;
  font-weight: bold;
}
.card-title {
  color: rgb(255, 255, 255);
  font-family: "Montserrat", sans-serif;
  font-weight: 600;
}
</style>
