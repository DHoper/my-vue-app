<template>
  <div class="container">
    <div id="message">{{getData}}</div>
    <button @click="sendToParent">发送</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      getData: ""
    }
  },
  mounted() {
    window.onload = () => {
      window.addEventListener('message', function (e) {
        this.getData = e.data;
        // window.document.getElementById('message').innerHTML = e.data.name;
        console.log(e.data);

      }, false)
    }
  },
}
</script>