<template lang='pug'>
  h1 {{user.name}}
</template>
<script>
import { resolve } from 'q'
export default {
  validate({params}){
// проверка валидации на число
    return /^\d+$/.test(params.id)
  },
  asyncData({params, error}){
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        reject(error(new Error('User not found')))
        // resolve({
        //   user: {
        //     name: `Test user ${params.id}`
        //   }
        // })
      }, 1500)
    })
  }
}
</script>