<template>
  <button
    class="button"
    :class="btnStyle"
    v-bind="$attrs"
    v-on="$listeners"><slot /></button>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    btnStyle: {
      type: String,
      default: ''
    }
  }
}
</script>


<style scoped>
.button {
  font: inherit;
  background-color: rgb(13, 82, 122);
  color: white;
  padding: 5px;
  cursor: pointer;
  border: 1px solid black;
  border-radius: 5px;
}

.button:hover,
.button:active {
  background-color: rgb(51, 51, 51);
  border: 1px solid rgb(54, 131, 231);
  color: rgb(236, 222, 89);
}

.inverted {
  background-color: white;
  color: black;
  border: 1px solid transparent;
}

.inverted:hover,
.inverted:active {
  color: #ccc;
  background-color: white;
  border: 1px solid transparent;
}

.cancel {
  background-color: rgb(196, 13, 13);
  color: white;
  border: 1px solid transparent;
}

.cancel:hover,
.cancel:active {
  background-color: salmon;
  border: 1px solid transparent;
  color: white;
}
</style>
