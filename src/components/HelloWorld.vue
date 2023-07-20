<template>
  <div class="container">
    <div id="message"></div>
    <button @click="sendToParent">发送</button>
  </div>
</template>
<script>
export default {
  mounted () {
    window.onload = () => {
      window.addEventListener('message', function (e) {

        window.document.getElementById('message').innerHTML = e.data.name;
        console.log(88888);
        
      }, false)
    }
  },
}
</script>