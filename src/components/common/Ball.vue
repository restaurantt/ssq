<template>

    <span v-bind:class="{ bluebg: isRedBg==false }">{{ number }}</span>

</template>

<script>
export default {
  name: 'Ball',
  props: {
    number: Number,
    isRed: Boolean
  },
  computed: {
    isRedBg: function () {
      return this.isRed
    }
  }
}

</script>

<style scoped>
span {
  background-color: red;
  font-size:22px;
  color:white;
  width:40px;
  height:40px;
  text-align:center;
  line-height:2;
  border-radius:50%;
  margin:2px;
  display:inline-block;
}
.bluebg {
  background-color: blue;
}
</style>
