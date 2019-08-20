<template>
  <div id="app">
    <Branch v-for="branch in branchData" :key="branch.description" :children="branch.children">
      <h1>{{branch.description}}</h1>
    </Branch>
  </div>
</template>

<script>
/* eslint no-dupe-keys: 0 */
import Branch from './components/Branch'

export default {
  name: 'app',
  components: {
    Branch
  },
  data: function () {
    return {
      branchData: [
        {          description: '1', children:
            [{
              description: '1.1', children: [],
              description: '1.2', children: [
                {
                  description: '1.2.1', children: [],
                  description: '1.2.2', children: [],
                }
              ]
            }]
        },
        { description: '2', children: [] },
        { description: '3', children: [] },
      ]
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>
