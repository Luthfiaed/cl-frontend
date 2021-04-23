<template>
  <div>
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

.button--blue {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #2a296c;
  color: #2a296c;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 20px;
}

.button--blue:hover {
  color: #fff;
  background-color: #2a296c;
}

.button--blue-2 {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #2a296c;
  color: #fff;
  background-color: #2a296c;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--blue-2:hover {
  color: #2a296c;
  background-color: #fff;
}

.button--red {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #d12525;
  color: #fff;
  background-color: #d12525;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--red:hover {
  color: #d12525;
  background-color: #fff;
}

.logo-non-root {
  position: absolute;
  top: 30%;
  left: 35%;
}

.links-non-root {
  position: absolute;
  top: 65%;
  left: 37%;
}

.title-non-root {
  font-family: 'Poppins';
  color:  #2354a1;
  font-size: 42px;
  position: absolute;
  top: 50%;
  left: 38%;
}
</style>
