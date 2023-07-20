<template>
  <div class="container">
    <h1>01</h1>
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
    window.onload = () => {
      window.addEventListener('message', function (e) {
        this.data = e.data;
        // window.document.getElementById('message').innerHTML = e.data.name;
       alert(e.data,777,this.data);

      }, false)
    }
  },
}
</script>