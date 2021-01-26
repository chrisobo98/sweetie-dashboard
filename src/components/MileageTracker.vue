<template>
  <div>
    <v-data-table
      :headers="headers"
      :items="desserts"
      item-key="name"
      class="elevation-1"
      :search="search"
      :custom-filter="filterOnlyCapsText"
    >
      <template v-slot:top>
        <v-text-field
          v-model="search"
          label="Search (use that good ol' uppercase or it doesn't work)"
          class="mx-4"
        ></v-text-field>
      </template>
      <template v-slot:body.append>
        <tr>
          <td></td>
          <td>
            <v-text-field
              v-model="miles"
              type="number"
              label="Less than"
            ></v-text-field>
          </td>
          <td colspan="4"></td>
        </tr>
      </template>
    </v-data-table>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        search: '',
        miles: '',
        desserts: [
          {
            name: 'Ford of Richland',
            miles: 159,
            starting: 6.0,
            ending: 24,
            destination: 4.0,
            purpose: '1%',
          },
          {
            name: 'Rick Myers Chevy of Richland',
            miles: 237,
            starting: 9.0,
            ending: 37,
            destination: 4.3,
            purpose: '1%',
          },
          {
            name: 'Roanoke Mazda',
            miles: 262,
            starting: 16.0,
            ending: 23,
            destination: 6.0,
            purpose: '7%',
          },
          {
            name: 'RAM, & Jeep of Roanoke',
            miles: 305,
            starting: 3.7,
            ending: 67,
            destination: 4.3,
            purpose: '8%',
          },
          {
            name: 'Gingerbread',
            miles: 356,
            starting: 16.0,
            ending: 49,
            destination: 3.9,
            purpose: '16%',
          },
        ],
      }
    },
    computed: {
      headers () {
        return [
          {
            text: 'Dealership',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          {
            text: 'miles in total',
            value: 'miles',
            filter: value => {
              if (!this.miles) return true

              return value < parseInt(this.miles)
            },
          },
          { text: 'starting (miles)', value: 'starting' },
          { text: 'ending (miles)', value: 'ending' },
          { text: 'destination', value: 'destination' },
          { text: 'purpose', value: 'purpose' },
        ]
      },
    },
    methods: {
      filterOnlyCapsText (value, search) {
        return value != null &&
          search != null &&
          typeof value === 'string' &&
          value.toString().toLocaleUpperCase().indexOf(search) !== -1
      },
    },
  }
</script>