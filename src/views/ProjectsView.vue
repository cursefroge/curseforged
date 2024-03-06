<template>
    <div class="grid grid-cols-3 gap-4">
      <div 
        v-for="(item, index) in items" 
        :key="index"
      >
      <a :href=item.link>
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
            "name": "Y",
            "description": "X, but better.",
            "link": "https://example.com"
          },
        ]
      }
    }
  }
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
}
h3 {
    font-size: 1.5rem;
    font-weight: 500;
    margin-bottom: 0.5rem;
}
a {
  color: inherit;
}
a:hover {
  background: var(--vt-c-black)
}
</style>