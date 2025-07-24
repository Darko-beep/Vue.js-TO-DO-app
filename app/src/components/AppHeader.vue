<template>
  <header>
    <h1><span></span> To Do App</h1>
    <p>Building Real World Web Application with Vue.js 3</p>
  </header>
</template>

<style scoped>
header {
  border-bottom: 1px solid #ccc;
  background-color: black;
}
header::after {
  content: ' ';
  display: block;
  height: 1px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.75);
}
h1 {
  font-size: 2rem;
}
h1.icon {
  font-size: 1rem;
  /* vertical-align: midddle; */
}
</style>
