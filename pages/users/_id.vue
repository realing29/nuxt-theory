<template>
  <h1>User {{$route.params.id}}</h1>
</template>
<script>
export default {
  validate({params}){
// проверка валидации на число
    return /^\d+$/.test(params.id)
  }
}
</script>