<template>
  <div class="container">
    <h1>B</h1>
    <div>{{data}}</div>
    <div id="message"></div>
    <button @click="getData">取得資料</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      data: ""
    }
  },
  methods: {
    getData() {
      window.addEventListener('message', function (e) {
        console.log(e.data,777);
        this.data = e.data;
        window.document.getElementById('message').innerHTML = e.data;
      }, false)
    }
  },
  // mounted() {
  //   window.onload = () => {
  //     window.addEventListener('message', function (e) {
  //       this.getData = e.data;
  //       // window.document.getElementById('message').innerHTML = e.data.name;
  //       console.log(e.data,777);

  //     }, false)
  //   }
  // },
}
</script>