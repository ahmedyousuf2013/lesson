// AccountInfo.vue

<template>
 <div id='account-info'>
     <button @click='changeUsername()'>Change Username</button>
   {{username}}
 </div>
</template>
 
<script>
export default {
    name:"account-info",

 props: ['username'],
  methods: {
   changeUsername() {
       debugger
     this.$emit('changeUsername', 'mattmaribojoc')
   }
 }
}
</script>