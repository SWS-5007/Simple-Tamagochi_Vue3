<template>
  <footer>
    <p :class="$style['powered-wrapper']">
      Powered by
      <a :class="$style['powered-link']" href="https://v3.vuejs.org/">
        <img :class="$style['powered-logo']" src="/images/vue-logo.svg" alt="Vue.js logo" />
        Vue.js 3
      </a>
      <span>, </span>
      <a :class="$style['powered-link']"
        href="https://www.netlify.com/?utm_source=github&utm_medium=gigavue-bh&utm_campaign=devex">
        <img :class="$style['powered-logo']" src="/images/netliheart.svg" alt="Netlify Heart Logo" />
        Netlify
      </a>
      <span> & </span>
      <a :class="$style['powered-link']" href="https://www.github.com/bencodezen/giga-vue">
        <img :class="$style['powered-logo']" src="/images/github-logo.svg" alt="GitHub Logo" />
        GitHub</a>
    </p>
  </footer>
</template>

<style module>
.powered-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 15px;
  font-weight: 500;
}

.powered-link {
  padding: 0 5px;
  text-decoration: none;
  color: #34495e;

  &:hover {
    text-decoration: underline;
  }
}

.powered-link:first-child,
.powered-link:last-child {
  padding-right: 0;
}

.powered-logo {
  width: 18px;
}
</style>
