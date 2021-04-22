<template>
  <router-view />
</template>

<style lang="scss">
@import "@/assets/sass/button.scss";
// @import "@/assets/sass/font.scss";

// @import "@/vendor/css/normalize.min.css";


* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Inter', sans-serif;
}

button:focus {
  outline: none;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.display-none {
  display: none;
}

@font-face {
  font-family: 'Inter';
  src: url('./assets/fonts/Inter-Regular.ttf');
  src: local('Inter Regular'), local('Inter-Regular'),
      url('./assets/fonts/Inter-Regular.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'Inter';
  src: url('./assets/fonts/Inter-Medium.ttf');
  src: local('Inter Medium'), local('Inter-Medium'),
      url('./assets/fonts/Inter-Medium.ttf') format('truetype');
  font-weight: 500;
  font-style: normal;
}

@font-face {
  font-family: 'Inter';
  src: url('./assets/fonts/Inter-SemiBold.ttf');
  src: local('Inter Semi Bold'), local('Inter-SemiBold'),
      url('./assets/fonts/Inter-SemiBold.ttf') format('truetype');
  font-weight: 600;
  font-style: normal;
}
</style>



