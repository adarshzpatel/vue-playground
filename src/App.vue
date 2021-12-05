<template>
 <h1>Hello</h1>
 <Button color='primary'>Primary</Button>
 <Button color='secondary'>Secondary</Button>
 <Button color='info'>Info</Button>
 <Button @click="toggleDarkMode" color='secondary'>Toogle Dark Mode</Button>
</template>

<script>
import Button from "./components/Button.vue"
export default {
  name: 'App',
  methods: {
    toggleDarkMode(){
      const app = document.getElementById('app');
      if(app.classList.contains('dark')){
        app.classList.remove('dark');
      } else {
        app.classList.add('dark');
      }
    }
  },
  components: {
    Button
}
}
</script>

<style lang="scss">

*{
  margin: 0;
  padding: 0;
}

:root {
  --background: #fffffe !important;
  --primary:#4FC4CF !important;
  --primary-light:#77D1DA !important;
  --primary-dark:#32ADB8 !important;
  --secondary: #994ff3 !important;
  --secondary-light:#B47EF6 !important;
  --secondary-dark:#7D1FEF !important;
  --text-primary: #181818 !important;
  --info: #00b0ff !important;
  --info-light: #33bfff !important;
  --info-dark: #007bb2;

}

.dark{
  --background: #16161a !important;
  --primary: #2cb67d !important;
  --primary-light:#42D196 !important;
  --primary-dark:#228C60 !important;
  --secondary: #7f5af0 !important;
  --secondary-light:#A489F5 !important;
  --secondary-dark:#5D2DEB !important;
  --text-primary: #fffffe !important;
   --info: #00b0ff !important;
  --info-light: #33bfff !important;
  --info-dark: #007bb2;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  gap: 1rem;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  color: var(--text-primary);
  background: var(--background);
}
</style>
