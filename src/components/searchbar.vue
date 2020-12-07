<template>
  <div>
    <h2>Sva jela uzeta sa api-a</h2>
    <input
      type="text"
      v-model="ime"
      placeholder="Unesite ime ili dio imena jela (na engleskom)"
    />
    <ul>
      <li v-for="(jela, index) in filtrirano" :key="index">
        <a :href="'#a'+jela.recipe.yield+jela.recipe.dietLabels[0]"><pre>{{ jela.recipe.label }}</pre></a>
        <!-- ne ako ide van stranice onda je baš aj da se sam ubacim kod zorane u vjezbeaj -->
      </li>
    </ul>
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

    let response = await fetch("https://api.edamam.com/search?q=main&app_id=0668221e&app_key=9c7c1b04cbabda98396715575c6223c2")

    if (response.ok) {
      const resp = await response.json()
      this.jela = resp.hits
    } else {
      alert("HTTP-Error: " + response.status);
    }
  },
  computed: {

    filtrirano() {
      let filtered = []
      if (this.jela)
        filtered = this.jela.filter((item) =>
          item.recipe.label.toLowerCase().includes(this.ime.toLowerCase())
        )

      return filtered;
    },
  },
};
</script>

<style scoped>
pre{padding-top: 50px;}
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