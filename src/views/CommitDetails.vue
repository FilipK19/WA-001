<template>
  <div class="commit">
    <h1>Detalji Commita</h1>
    <ul>
      <li>Ime autora: {{commit.commit.author.name}}</li>
      <li>Vrijeme: {{commit.commit.author.date}}</li>
      <li>Poruka: {{commit.commit.message}}</li>
      
    </ul>
  </div>
</template>

<script>
export default {
  name: "CommitDetails",
  props: ["sha"],

  data: function () {
    return {
      commit:[],
    }
  },

  created: async function() {
    let rezultat = await fetch(
      'https://api.github.com/repos/vuejs/vue/commits/' + this.sha)
    let podaci = await rezultat.json();

    this.commit = podaci
}

}
</script>

