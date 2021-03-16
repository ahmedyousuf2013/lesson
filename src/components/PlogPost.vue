<template>
<div>

    <!-- <span>
        {{title}}
    </span>
    <span>
      likes Number :  {{like}}
    </span> -->

    <span> {{author.id +author.title }}</span>
</div>
    
</template>
<script>
export default {
    name:"plog-post",
    props:{

        title :String,
        like :Number,
        author: Object,
    }
    
}
</script>