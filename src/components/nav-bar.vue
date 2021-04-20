<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="ml-lg-5 ml-3" href="https://www.projucti.com">
      <img
        class="navbar-brand img m-2"
        alt="projucti-logo"
        height="30"
        src="../assets/projucti-logo-dark.png"
      />
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav ml-auto mr-lg-5 mr-3">
        <li class="nav-item">
          <a
            class="nav-link"
            target="_blank"
            href="https://www.facebook.com/projucti.tech"
          >
            <font-awesome-icon size="2x" :icon="['fab', 'facebook']" />
          </a>
        </li>
        <li class="nav-item">
          <a
            class="nav-link"
            target="_blank"
            href="https://twitter.com/Projucti1"
            ><font-awesome-icon size="2x" :icon="['fab', 'twitter']"
          /></a>
        </li>
        <li class="nav-item">
          <a
            class="nav-link"
            target="_blank"
            href="https://www.linkedin.com/company/projucti/"
            ><font-awesome-icon size="2x" :icon="['fab', 'linkedin']"
          /></a>
        </li>
        <li class="nav-item">
          <a
            class="nav-link"
            target="_blank"
            href="https://www.instagram.com/projucti_2020/"
            ><font-awesome-icon size="2x" :icon="['fab', 'instagram']"
          /></a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style>
</style>