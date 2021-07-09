<template>
  <div id="app">
    <input type="text" v-model="text" />
    <button @click="$router.push({ text })" class="user_btn">住所自動入力</button>
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
  async created() {
    const item = await axios.get(
      'curl https://apis.postcode-jp.com/api/v4/postcodes/1000001 \
  -G -v \
  -d "apikey=scXXQD1i29VdtnFS1QOuruB2oG6GIyNseCmaqEW"'
    );
    const postCode =item.data;
    this.postcode = postCode.postcode;
  }
};
</script>
