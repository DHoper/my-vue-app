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
      data: {}
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
      console.log(this.data);
      this.data = e.data;
      console.log("資料成功接收", this.data);
    }, false)

  },
}
</script>

<style>
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

li {
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 8px;
  margin-bottom: 8px;
}

li:hover {
  background-color: #f2f2f2;
}

div {
  margin-bottom: 4px;
}

div:last-child {
  margin-bottom: 0;
}
</style>