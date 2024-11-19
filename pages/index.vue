<template>
index.vue
{{isAllow}}
</template>

<script setup>
const isAllow=ref("")

onMounted(()=>{
  if("wakeLock" in navigator){navigator.wakeLock.request("screen").then((res)=>{
    isAllow.value="画面ロックさせない制御中"})
  }else{
    isAllow.value="画面ロック制御非対応"
  }
})

</script>