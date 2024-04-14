<template>
  <div>
    <Banner />
    <BurgerForm />
  </div>
</template>

<script>
import Banner from '../components/Banner'
import BurgerForm from '../components/BurgerForm'

export default {
  name: 'Home',
  components: {
    Banner,
    BurgerForm
  }
}
</script>