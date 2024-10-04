<template>
  <div class="homepage-content">
    <h1>Here comes the content of HomePage.</h1>


    <button 
      class="base-btn" 
      :style="getButtonStyles('primary', false)"
      :disabled="false"
    >
      <slot /> BaseButton
    </button>

    <button
      class="base-btn"
      :style="getButtonStyles('warn', true)"
      :disabled="true"
    >
      <slot /> BaseButton disabled
    </button>

    <button
      class="base-btn"
      :style="getButtonStyles('warn', false)"
      :disabled="false"
    >
      <slot /> BaseButton with color props
    </button>
    <button
      class="base-btn"
      :style="getButtonStyles('danger', false)"
      :disabled="false"
    >
      <slot /> BaseButton with color props
    </button>
  </div>
</template>

<script>
const colorPalette = {
  primary: { bg: '#42b983', hoverBg: '#4cce93', focusBorder: '#47b696' },
  warn: { bg: '#ff5722', hoverBg: '#ff7043', focusBorder: '#ff8a65' },
  danger: { bg: '#e53935', hoverBg: '#ef5350', focusBorder: '#e57373' },
};

export default {
  methods: {
    getButtonStyles(color, isDisabled) {
      const palette = colorPalette[color] || colorPalette.primary;
      return {
        backgroundColor: isDisabled ? '#cccccc' : palette.bg,  
        cursor: isDisabled ? 'not-allowed' : 'pointer',
        opacity: isDisabled ? 0.6 : 1,  
      };
    },
  },
};
</script>

<style scoped>
.homepage-content {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 10px;
}

.base-btn {
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  width: 150px;
  transition: all 0.2s ease-in-out;
}

.base-btn:hover {
  transform: scale(1.1);
  transition: all 0.1s ease-in-out;
}
.base-btn:focus {
  outline: none;
  color: black;
}
</style>
