<template>
  <div>
      <nav
      class="navbar is-info"
      role="navigation"
      aria-label="main navigation"
    >
      <div class="navbar-brand">
        <nuxt-link
          class="navbar-item"
          to="/"
        >
          AAIEEK!
        </nuxt-link>
        <a
          role="button"
          class="navbar-burger burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
        >
          <span aria-hidden="true"/>
          <span aria-hidden="true"/>
          <span aria-hidden="true"/>
        </a>
      </div>
      <div class="navbar-menu">
        <div class="navbar-start">
          <nuxt-link
            to="/"
            class="navbar-item"
          >Top Trending</nuxt-link>
          <nuxt-link
            to="/new"
            class="navbar-item"
          >Newly Added</nuxt-link>
          <nuxt-link
            to="/submit"
            class="navbar-item"
          >New Submit</nuxt-link>
        </div>
        <div class="navbar-end">
        <div class="navbar-item">
        <div class="buttons">
        <nuxt-link
          v-if="!$auth.loggedIn"
          to="/register"
          class="button is-primary"
        >
          <strong>Register</strong>
        </nuxt-link>
        <nuxt-link
          v-if="!$auth.loggedIn"
          to="/login"
          class="button is-light"
        >Log in</nuxt-link>
        <button
          v-else
          class="button is-light"
          @click="$auth.logout()"
        >Log out</button>
       </div>
       </div>
       </div>
      </div>
    </nav>
    <Nuxt />
  </div>
</template>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
