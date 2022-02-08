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
                    <button>Szerkesztés</button>
                    <button @click="deleteStatue(statue.id)">Törlés</button>
                </td>
            </tr>
            <tr>
                <td>
                    <input type="text" v-model="statue.person">
                </td>
                <td>
                    <input type="number" v-model="statue.height">
                </td>
                <td>
                    <input type="number" v-model="statue.price">
                </td>
                <td>
                    <button @click="newStatue">Mentés</button>
                    <button @click="clearForm">Mégse</button>
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
            statue: {
                id: null,
                person: '',
                height: '',
                price: ''
            },
            statues: []
        }
    },
    methods: {
        async loadData() {
            let Response = await fetch('http://127.0.0.1:8000/api/statues');
            let data = await Response.json();
            this.statues = data;
        },

        async newStatue() {
            await fetch('http://127.0.0.1:8000/api/statues', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'Accept': 'application/json'
                },
                body: JSON.stringify(this.statue)
            });
            await this.loadData();
            this.clearForm();
        },

        async deleteStatue(id) {
            let Response = await fetch(`http://127.0.0.1:8000/api/statues/${id}`, {
                method: 'DELETE'
            });
            console.log(Response);
            await this.loadData();
        },

        clearForm() {
            this.statue = {
                id: null,
                person: '',
                height: '',
                price: ''
            };
        }
    },
    mounted() {
        this.loadData();
    }
}
</script>