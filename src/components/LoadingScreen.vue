<template>
  <div :class="{ loader: true, fadeout: !isLoading }">
    <div>
      <div class="lds-dual-ring"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "loading",
  props: ["isLoading"],
};
</script>

<style lang="scss" scoped>
.loader {
  background-color: #1e2d3b;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;

  .lds-dual-ring {
    display: inline-block;
    width: 80px;
    height: 80px;
  }
  .lds-dual-ring:after {
    content: " ";
    display: block;
    width: 64px;
    height: 64px;
    margin: 8px;
    border-radius: 50%;
    border: 6px solid #1ed760;
    border-color: #1ed760 transparent #1ed760 transparent;
    animation: lds-dual-ring 1s linear infinite;
  }
  @keyframes lds-dual-ring {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
}

.fadeout {
  animation: fadeout 3s forwards;
}

@keyframes fadeout {
  to {
    opacity: 0;
    visibility: hidden;
  }
}
</style>
