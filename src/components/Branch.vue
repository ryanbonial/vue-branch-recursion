<template>
  <div>
    <slot />
    <Branch v-for="branch in children" :key="branch.description" :children="branch.children">
      <h1>{{branch.description}}</h1>
    </Branch>
  </div>
</template>

<script>
export default {
  name: 'Branch',
  props: {
    children: Array
  }
}
</script>

<style>
</style>