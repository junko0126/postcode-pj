<template>
  <div id="app">
    <input type="text" v-model="text" />
    <button @click="userClick" >住所自動入力</button>
    <p>Address:{{ text }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return{
      text: ""
    };
  },
  methods: {
    userClick() {
      this.text
    },
    async mounted
    const item = axios.get(
      `https://apis.postcode-jp.com/api/v4/postcodes/1000001?apikey=scXXQD1i29VdtnFS1QOuruB2oG6GIyNseCmaqE`
    );console.log(item);
    
    const postCode =item.data;
    this.postcode = postCode.postcode;
    this.text = postCode.AllAddress;
  }
};
</script>