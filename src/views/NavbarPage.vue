<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <router-link class="navbar-brand" to="/">Clinic</router-link>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarNav"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <router-link class="nav-link" :class="{ active: $route.path === '/' }" to="/"
            >Home</router-link
          >
        </li>

        <li class="nav-item">
          <router-link class="nav-link" :class="{ active: $route.path === '/about' }" to="/about"
            >About</router-link
          >
        </li>

        <li class="nav-item">
          <router-link
            class="nav-link"
            :class="{ active: $route.path === '/contact' }"
            to="/contact"
            >Contact Us</router-link
          >
        </li>

        <li class="nav-item">
          <router-link
            class="nav-link"
            :class="{ active: $route.path === '/doctors' }"
            to="/doctors"
            >Doctors</router-link
          >
        </li>
      </ul>
    </div>
  </nav>
</template>
