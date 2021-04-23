<template>
    <div class="container">
    <div class="logo-non-root">
      <Logo />
    </div>
    <div>
      <h1 class="title-non-root">
        Tenant Data
      </h1>
      <div class="links-non-root">
        <nuxt-link
          to="/tenants/create"
          rel="noopener noreferrer"
          class="button--blue"
        >
          Create
        </nuxt-link>
        <nuxt-link
          to="/tenants/list"
          rel="noopener noreferrer"
          class="button--blue"
        >
          List
        </nuxt-link>
      </div>
    </div>
    </div>
</template>