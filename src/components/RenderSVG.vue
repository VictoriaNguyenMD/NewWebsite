<template>
  <a href="{{item.link}}">
    <img src="{{item.icon}}" />
  </a>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "RenderSVG",
});
</script>
