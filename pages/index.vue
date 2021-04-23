<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        Central License
      </h1>
      <div class="links">
        <nuxt-link
          to="/tenants"
          rel="noopener noreferrer"
          class="button--blue"
        >
          Tenant
        </nuxt-link>
        <nuxt-link
          to="/license"
          rel="noopener noreferrer"
          class="button--blue"
        >
          License
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Poppins',
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 64px;
  color: #2354a1;
  letter-spacing: 1px;
  margin-bottom: 20px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
