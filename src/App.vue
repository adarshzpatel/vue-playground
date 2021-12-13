<template>
  <div class="container">
    <button class="primary-light">Primary Light</button>
    <button>Primary</button>
    <button class="primary-dark">Primary Dark</button>
  </div>
<p>Hue : {{hue}} </p>
  <input v-model="hue" type="range" max="360"  name="hue" id="hue" />
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      hue: 0,
    };
  },
  watch:{
    // setTheme(){
      hue(){
        document.documentElement.style.setProperty('--primary-h',this.hue);
        }
    // }
  }
};
</script>

<style lang="scss">
:root {
  /* Constants */
  --lightnessTransform: 10%;
  /* Base Values */
  --primary-h: 180;
  --primary-s: 100%;
  --primary-l: 40%;

  /* Variant Values */
  --primary-light-l: calc(var(--primary-l) + var(--lightnessTransform));
  --primary-dark-l: calc(var(--primary-l) - var(--lightnessTransform));
  /* Composed Primary Color*/
  --primary: hsl(var(--primary-h), var(--primary-s), var(--primary-l));
  /* Primary Light Variant */
  --primary-light: hsl(
    var(--primary-h),
    var(--primary-s),
    var(--primary-light-l)
  );
  --primary-dark: hsl(
    var(--primary-h),
    var(--primary-s),
    var(--primary-dark-l)
  );
  --text-color: white;
  --border-radius: 4px;
}
button {
  background: var(--primary);
  padding: 12px 16px;
  border-radius: var(--border-radius);
  border: none;
  color: var(--text-color);
  font-size: larger;
  white-space: nowrap;
  &:hover {
    transition: all 0.3s ease-out;
    background: var(--primary-light);
  }
  &:active {
    transition: all 0.3s ease-out;
    transform: translateY(2px);
    background: var(--primary-dark);
  }
}

.primary-light {
  background: var(--primary-light);
}

.primary-dark {
  background: var(--primary-dark);
}

.container {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin:1rem;
}
</style>
