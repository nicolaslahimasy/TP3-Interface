<template>
  <BaseButton
    :disabled="isPending"
    :style="buttonStyles"
    :color="color"
    @click.stop.prevent="handleClick"
  >
    <example-icon
      v-if="isPending"
      pulse
    />
    <slot />
  </BaseButton>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  name: 'AsyncButton',
  components: {
    BaseButton,
  },
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary',
    }
  },  

  data() {
    return {
      isPending: false
    }
  }, 

  computed: {
    buttonStyles() {
      return {
        cursor: this.isPending ? 'not-allowed' : 'pointer',  
      };
    }
  },

  methods: {
    async handleClick() {
      const originalOnClick = /** @type {() => Promise<void>} */ (this.$attrs.click || (() => Promise.resolve()));
      this.isPending = true;

      originalOnClick()
        .finally(() => {
         
          setTimeout(() => {
            this.isPending = false;
          }, 2000); 
        });

   
      this.$emit('click');
    }
  }
};  
</script>
