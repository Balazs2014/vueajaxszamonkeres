<template>
  <div>
      <h1>Statues</h1>
      <table>
        <thead>
            <tr>
                <th>Személy</th>
                <th>Magasság</th>
                <th>Ár</th>
                <th>Műveletek</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="statue in statues" v-bind:key="statue.id">
                <td>{{ statue.person }}</td>
                <td>{{ statue.height }}</td>
                <td>{{ statue.price }}</td>
                <td>
                    <button>Módosítás</button>
                    <button>Törlés</button>
                </td>
            </tr>
        </tbody>
      </table>
  </div>
</template>

<script>
export default {
  name: 'Statues',
  data()  {
      return {
        statues: []
      }
  },
  methods: {
      async loadData() {
          let Response = await fetch('http://127.0.0.1:8000/api/statues');
          let data = await Response.json();
          this.statues = data;
      }
  },
  mounted() {
    this.loadData();
  }
}
</script>