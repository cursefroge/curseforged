<template>
  <div v-for="(item, index) in items" :key="index"  class="grid grid-cols-3 gap-4">
      <div>
        <a :href="item.link">
          <h3>{{ item.name }}</h3>
          {{ item.description }}
        </a>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: 'dosu',
          description: 'Passwordless setuid made in 91 lines',
          link: 'https://github.com/cursefroge/dosu',
        },
      ],
    };
  },
};
</script>
<style scoped>
.grid {
  margin-top: 2rem;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.grid > div {
  color: white;
  /*border: 1px solid var(--color-border);*/
  box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
  border-radius: 10px; /* Add rounded corners */
  padding: 1rem; /* Add some padding */
  background-color: var(--vt-c-black-muted); /* Add a background color */
  justify-items: center;
  align-items: center;
  display: flex;
  flex-direction: column;
  text-align: center;
  /* the background translucent, just blurred */
  backdrop-filter: blur(20px);
}
h3 {
  font-size: 1.5rem;
  font-weight: 500;
  margin-bottom: 0.5rem;
}
a {
  color: var(--vt-c-white), 
}
a:hover {
  /* background no opacity */
  background-color: transparent;
}
</style>
