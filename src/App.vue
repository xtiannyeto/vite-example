<template>
  <Card />
</template>

<script setup lang="ts">
import { defineComponent, ref } from '@vue/runtime-core';
import Card from './components/Card.vue';

defineComponent({
  components: { Card }
});
</script>
