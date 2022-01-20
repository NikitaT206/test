<template>
  <div class="container">
    <div class="image-container">
      <img class="image">
    </div>
  </div>
   <li class="li">
   <p>{{account.avatar}}</p>
  </li>
</template>

<script>
export default {
  props: {
    account: {
      type: Object,
      required: true
    }
  }
}
</script>

<style >

</style>

