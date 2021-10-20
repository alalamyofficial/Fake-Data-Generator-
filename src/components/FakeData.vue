<template>
  <div>
    <h2 class="bg-gray-100 border shadow text-center font-bold">Fake Data Generator</h2>

    <div v-for="user in users.results" :key="user.id">
      <div
        class="mt-3 mb-2 p-1 bg-gray-50  w-full
        grid justify-items-center"
      >
        <img
          class="rounded-full border shadow mb-3"
          :src="user.picture.large"
          alt=""
        />
        <div class="ml-3 text-center">
          <p class="font-bold">{{ user.name.title }} : {{ user.name.first }} {{ user.name.last }}</p>
          <br />
          <br />

          <div class="flex">
            <div class="">
              <div class="flex">
                <label class="mr-2" for="">Gender : </label>
                {{ user.gender }} <br />
              </div>

              <div class="flex">
                <label class="mr-2" for="">Location : </label>
                {{ user.location.street.number }}
                {{ user.location.street.name }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">City : </label>
                {{ user.location.city }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">State : </label>
                {{ user.location.state }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">Country : </label>
                {{ user.location.country }}
              </div>
              <div class="flex">
                <label class="mr-2" for="">Postcode : </label>
                {{ user.location.postcode }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">Offest : </label>
                {{ user.location.timezone.offset }}
              </div>
              <div class="flex">
                <label class="mr-2" for="">Description : </label>
                {{ user.location.timezone.description }}
              </div>
            </div>
            <!-- ------------ -->
            <div class="ml-6">
              <div class="flex">
                <label class="mr-2" for="">Latitude : </label>
                {{ user.location.coordinates.latitude }}
              </div>
              <div class="flex">
                <label class="mr-2" for="">Longitude : </label>
                {{ user.location.coordinates.longitude }}
              </div>
              <div class="flex">
                <label class="mr-2" for="">Email : </label>
                {{ user.email }}
              </div>
              <div class="flex">
                <label class="mr-2" for="">Birthday : </label>
                {{ user.dob.date }}
              </div>
              <div class="flex">
                <label class="mr-2" for="">Age : </label>
                {{ user.dob.age }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">Phone : </label>
                {{ user.phone }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">Cell Phone : </label>
                {{ user.cell }}
              </div>

              <div class="flex">
                <label class="mr-2" for="">Nationality : </label>
                {{ user.nat }}
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="ml-4 mt-2 mb-2 p-1"></div>

      <div class="text-center"></div>
    </div>
    <br />

    <div class="grid justify-items-center">
      <button
        class="rounded-full border shadow font-bold 
        bg-indigo-400 hover:bg-indigo-300 p-3 text-center px-5"
        @click="getData"
      >
        Change
      </button>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      users: [],
    };
  },

  mounted() {
    this.getData();
  },

  methods: {
    getData() {
      axios.get("https://randomuser.me/api/?results=1").then((res) => {
        console.log(res);
        this.users = res.data;
      });
    },
  },
};
</script>

<style></style>
