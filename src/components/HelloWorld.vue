<template>
  <div class="container">
    <h1>0w</h1>
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
    // alert(777,this.data);
      window.addEventListener('message', function (e) {
        this.data = e.data.title;
        // let a = JSON.stringify(e.data);
        console.log(this.data, 755);
        window.document.getElementById('message').innerHTML = this.data;
        alert(777,a);

      }, false)
    
  },
}
</script>