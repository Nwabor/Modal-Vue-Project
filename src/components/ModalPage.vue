<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme2 === 'sale' }">
      <!-- <h1>{{ header }}</h1>
      <p>{{ text }}</p> -->
      <slot></slot>
      <div class="action">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme2"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.4);
  width: 100%;
  height: 100%;
}

p {
  font-style: italic;
}

.modal.sale {
  background: crimson;
  color: white;
}

.modal.sale h1 {
  color: white;
}
</style>
