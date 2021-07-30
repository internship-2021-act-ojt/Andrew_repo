<template>
  <div class="background">
    <img class="elonMusk", src="/elon.jpg">

    <div class="Below">
      <b>Elon Musk</b>
      The founder and CEO of Tesla
    </div>

  </div>
</template>

<script>
export default {}
</script>


<style scoped>
.background {
}

.Below {
  display: flex;
  flex-direction: column;
}

.elonMusk {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin-right: 20px;
}
</style>
