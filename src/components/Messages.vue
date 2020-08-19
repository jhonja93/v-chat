<template>
  <div class="vc-messages-container">
    <div class="vc-messages"></div>
  </div>
</template>

<script>
export default {
  name: 'VcMessages'
}
</script>

<style>
.vc-messages-container {
  height: 50vh;
  max-height: 410px;
  overflow-y: scroll;
  /* padding-top: 10px; */
  -webkit-overflow-scrolling: touch;
  background-color: #c0c0c0;
}
.vc-messages {
  border: 1px solid #000;
  height: 49vh;
  background: #fff;
  width: 97%;
  margin: auto;
  margin-top: 4px;
}
</style>