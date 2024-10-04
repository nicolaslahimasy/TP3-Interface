<template>
  <div class="homepage-content">
    <h1>Here comes the content of HomePage.</h1>
  </div>
  
  <button class="base-btn">
    <slot /> Base Button <!-- slot outlet -->
  </button>
</template>

<style scoped>
.homepage-content {
  display: grid;
  justify-items: center;
}
.base-btn {
  color: #fff;
  background-color: #42b983;
  border :none;
  padding: 5px 10px;
  margin: 5px;
  margin-left:48%;
  border-radius: 8px;
  cursor: pointer;
  display: flex;
  justify-content: center;
}
</style>
