<template>
    
  <div>
    <!--
    Listen for `childToParent`: the first parameter of the `$emit` method
    in the child component. We're also listening and reacting to an
    `increment` event - in this case, we increment a counter inline.
    -->
    <Child :parentData="myData" v-on:childToParent="onChildClick" v-on:increment="counter++"></Child>
  </div>
</template>
<script>
import Child from './Child.vue'
export default {
    data () {
    return {
      counter: 0,
      fromChild: '', // This value is set to the value emitted by the child
    }
  },
  name: 'about',
  components: {
    Child
  },
  methods: {
    // Triggered when `childToParent` event is emitted by the child.
    onChildClick (value) {
      this.fromChild = value
    }
  }
}
</script>