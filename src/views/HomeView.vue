<template>
  <div class="home">
    <RegisterForm/>
  </div>
</template>

<script>
// @ is an alias to /src
import RegisterForm from '@/components/Forms/RegisterForm'

export default {
  name: 'HomeView',
  components: {
    RegisterForm
  }
}
</script>
