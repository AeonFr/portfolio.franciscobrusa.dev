<template>
  <div class="negate-container">
    <slot>
      <!-- This will only be displayed if there is no content
      to be distributed.-->
    </slot>
  </div>
</template>
<script>
export default {
  name: 'negate-container'
}
</script>

<style>
  .negate-container{
    overflow: hidden;
    max-width: 100vw;
    margin-left: -1.99rem;
    margin-right: -1.99rem;
  }
  @media screen and (min-width: 44rem){
    .negate-container{
      margin-left: calc(-50vw + 20.99rem);
      margin-right: calc(-50vw + 20.99rem);
    }
  }
</style>