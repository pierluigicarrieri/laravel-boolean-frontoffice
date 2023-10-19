<script>
  export default {

  }
</script>

<template>
   <nav class="nav-bg">
    <div class="container">
      <div class="py-3 d-flex align-items-center">
        <h2>COCKTAILS</h2>

        <ul class="ms-auto d-flex list-unstyled gap-4">
          <li><RouterLink :to="{name: 'home'}" class="text-dark text-decoration-none">Home</RouterLink></li>
          <li><RouterLink :to="{name: 'chi-siamo'}" class="text-dark text-decoration-none">Chi-siamo</RouterLink></li>
          <li><RouterLink :to="{name: 'contatti'}" class="text-dark text-decoration-none">Contatti</RouterLink></li>
        </ul>
      </div>
    </div>
  </nav>

  <RouterView></RouterView>
</template>

<style>

</style>
