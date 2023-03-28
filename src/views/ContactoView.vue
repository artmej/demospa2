<template>
    <div>
        <h1>Gracias por Contactarnos</h1>
        <p>{{ message }}</p>
        <button id="list" onclick="list()">List</button>
    </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: ""
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/info")).json();
    this.message = text;
  }
};
</script>
