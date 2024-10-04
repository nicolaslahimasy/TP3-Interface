<template>
  <div class="homepage-content">
    <h1>Here comes the content of HomePage.</h1>
  
  
  <button class="base-btn">
    <slot /> BaseButton <!-- slot outlet -->
  </button>
  <button class="base-btn-disabled">
    <slot /> BaseButton disabled <!-- slot outlet -->
  </button>
</div>
</template>

<style scoped>
.homepage-content {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap:10px;
}
.base-btn {
  color: #fff;
  background-color: #42b983;
  border :none;
  padding: 5px 10px;
  border-radius: 8px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  width: 100px;
}

.base-btn:hover{
  transform: scale(1.2);
  transition: all 0.1s ease-in-out;
  animation-duration: 2s;
}
.base-btn:focus{
  background-color: brown;
}
.base-btn-disabled {
  color: #fff;
  background-color: #42b983;
  border :none;
  padding: 5px 10px;
  border-radius: 8px;
  cursor: disabled;
  display: flex;
  justify-content: center;
}
.base-btn-disabled{
  opacity: 0.6;
  cursor: not-allowed;
}

</style>
