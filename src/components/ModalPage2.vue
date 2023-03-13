<template>
  <div class="backdrop-2" @click.self="closedModal2">
    <div class="modal-2" :class="{ sale2: theme2 === 'sale2' }">
      <slot></slot>
      <div class="action2">
        <slot name="links2"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme2"],

  methods: {
    closedModal2() {
      this.$emit("closed");
    },
  },
};
</script>

<style scoped>
.modal-2 {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

.backdrop-2 {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.4);
  width: 100%;
  height: 100%;
}

.modal-2.sale2 {
  background-color: greenyellow;
}
</style>
