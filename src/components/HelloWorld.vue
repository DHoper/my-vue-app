<template>
  <div class="container">
    <h1>0w</h1>
    <ul>
      <li v-for="(user, index) in data" :key="user.id">
        <div>Custom ID: {{ user.custom_id }}</div>
        <div>Name: {{ user.name }}</div>
        <div>Email: {{ user.email }}</div>
        <div>Mobile: {{ user.mobile }}</div>
        <div>Status: {{ user.status }}</div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      data:{}
    }
  },
  // methods: {
  //   getData() {
  //     window.addEventListener('message', function (e) {
  //       console.log(e.data,777);
  //       this.data = e.data;
  //       document.getElementById('message').innerHTML = e.data;
  //     }, false)
  //   }
  // },
  mounted() {
    // alert(777,this.data);
      window.addEventListener('message', function (e) {
        data = e.data;
        console.log("資料成功接收", data);
      }, false)
    
  },
}
</script>