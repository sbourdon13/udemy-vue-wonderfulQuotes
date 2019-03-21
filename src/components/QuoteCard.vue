<template>
  <div>
    <div class="card p-3">
      <div class="quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script></script>

<style scoped>
.card {
  cursor: pointer;
}

.card:hover {
  background-color: rgb(255, 217, 217);
}

.quote {
  font-family: Arizonia, cursive;
  font-size: 1.3rem;
}
</style>
