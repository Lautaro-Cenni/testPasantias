<template>
<div>
  <Nav/>
  <Nuxt />
  <Footer/>
</div>
</template>

<script>
import Nav from "../components/layout/nav.vue"
import Footer from "../components/layout/footer.vue"

export default {
  components: {
    Nav,
    Footer
  }
 
}
</script>