<template>
  <div id="app">
    <header-menu/>
    <div class="container">
      <div class="row mt-2">
        <div class="col-8 mx-auto">
          <items/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import HeaderMenu from '@/components/Header'
import Items from '@/components/Items'

export default {
  name: 'App',
  components: {
    HeaderMenu,
    Items,
  }
}
</script>
