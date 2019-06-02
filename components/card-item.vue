<template>
  <div class="container-course__card-items">
    <div class="container-course__card-items-item">
      <span>{{ name }}:</span>
    </div>
    <div class="container-course__card-items-item-value">
      <span>{{ value }}</span>
    </div>
  </div>
</template>

<style>
.container-course__card-items {
  display: flex;
  flex-direction: row;
  border-bottom: 1px solid #cecece;
}

.container-course__card-items-item {
  font-weight: bold;
  width: 215px;
}

.container-course__card-items-item-value {
  width: 262px;
}
</style>

<script>
export default {
  name: 'CardItem',

  props: {
    name: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
  },
};
</script>
