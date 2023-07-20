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
      // 子页面接收消息
      window.addEventListener('message', function (e) {

        window.document.getElementById('message').innerHTML = e.data.name
        
      }, false)
    }
  },
  methods: {
    // 子页面发送消息
    sendToParent () {
      window.parent.postMessage({
        msg: 'hideselfService',
        key: '123456'
      }, '*')
    }
  }
}
</script>