<script setup lang="ts">
</script>

<template>
  <header id="header" bg-back dark="bg-#333333 border-dark" border-b shadow-sm />
</template>

<style>
#header {
  position: sticky;
  top: 0;
  left: 0;
  width: 100%;
  height: 48px;
  z-index: 9999999;
  box-sizing: border-box;
  padding: 15px;
  -webkit-backdrop-filter: saturate(180%) blur(20px);
  backdrop-filter: saturate(180%) blur(20px);
  display: flex;
}
</style>
