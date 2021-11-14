<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <NuxtLink to="/" class="nav-link active" aria-current="page" href="#">Home</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink to="/Blog" class="nav-link" href="#">Blog</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink to="/Portfolio" class="nav-link" href="#">Portfolio</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink to="/About" class="nav-link" href="#">About</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Condensed:wght@300;400;700&display=swap" rel="stylesheet">
    <Nuxt />
  </div>
</template>