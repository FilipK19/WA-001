<template>
  <div class="home">
  
  <ul>
    <li v-for="item in commits" v-bind:key="item.sha">
    Commit <router-link to="/about"> {{ item.sha }}</router-link>
    </li>
  </ul>
  </div>

</template>

<script>


export default {
  name: 'HomeView',
  data: function () {
    return {
      commits: [],
    };
  },
  async mounted() {
    let rezultat = await fetch(
      'https://api.github.com/repos/vuejs/vue/commits'
    );
    let podaci = await rezultat.json();

    //for (let item of podaci) {
    //  console.log(item.sha);
    //}
    this.commits = podaci;
  },

  }
</script>
