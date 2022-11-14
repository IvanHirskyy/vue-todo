<template>
    <div>
        {{taskItem.name}}
        {{taskItem.status}}
        {{taskItem.type}}
    </div>
</template>

<script>
     export default {
        props:['taskItem'],
    }
</script>