<template lang='pug'>
  h1 User {{$route.params.id}}
</template>
<script>
export default {
  validate({params}){
// проверка валидации на число
    return /^\d+$/.test(params.id)
  }
}
</script>