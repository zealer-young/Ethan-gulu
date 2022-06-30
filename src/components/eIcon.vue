<template>
  <svg class="icon" aria-hidden="true">
    <use :xlink:href="`#i-${name}`"></use>
  </svg>
</template>
<script>
import '../assets/icon'

export default {
  name: 'eIcon',
  props: ['name']
}
</script>
<style type="text/css">

.icon {
  width: 1em; height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}

</style>
