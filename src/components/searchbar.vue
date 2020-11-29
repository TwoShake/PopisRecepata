<template>
  <div>
    <h2>Sva jela uzeta sa api-a</h2>
    <input
      type="text"
      v-model="ime"
      placeholder="Unesite ime jela ili samo dio"
    />
    <ul>
      <li v-for="(jela, index) in filtrirano" :key="index">
        <pre>{{ jela }}</pre>
      </li>
    </ul>
    <pre>
      {{ filtrirano }}
    </pre>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jela: [],
      ime: "",
    };
  },
  async mounted() {

    let response = await fetch("https://api.edamam.com/search?q=main&app_id=0668221e&app_key=9c7c1b04cbabda98396715575c6223c2");

    if (response.ok) {
      this.jela = await response.json();
    } else {
      alert("HTTP-Error: " + response.status);
    }
  },
  computed: {

    filtrirano() {
      let filtered = [];
      if (this.jela)
        filtered = Object.keys(this.jela).filter((item) =>
          item.includes(this.ime)
        );

      return filtered;
    },
  },
};
</script>

<style scoped>
div {
  text-align: left;
}

ul {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  margin: 0;
  padding: 0;
}

li {
  display: block;
}

input {
  padding: 10px;
  margin-bottom: 20px;
  width: 100%;
}
</style>