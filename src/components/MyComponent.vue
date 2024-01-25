<template>
   <div>
    <v-app>
      <v-container>
        <v-autocomplete
            :items="items"
            density="comfortable"
            label="Escoja el firmante"
            return-object
            v-model="itemsSelected"
            item-title="title"
            item-value="id">
          <template v-slot:item="{ props, item }">
            <v-list-item
                v-bind="props"
                :subtitle="item.raw.id"
                :disabled="item.raw.disabled"
            ></v-list-item>
          </template>
        </v-autocomplete>
      </v-container>
      <v-btn text color="skyblue" @click="submit">OK</v-btn>
    </v-app>
  </div>

</template>

<script>
export default {
  name:  'MyComponente',
  data() {
    return {
    items: [ {
     title:  'Nombre 1',
      id: 'DAF',
     disabled: false,
    },
      {
      title:  'Nombre 2',
      id: 'DDT',
      disabled: true,
    },
      {
        title:  'Nombre 3',
        id: 'PRE',
        disabled: false,
      }
    ],
      itemsSelected: {title: null, id: null}
  }
  },
  mounted() {
    this.selectedClub = {id: null, name: null};
  },
  methods: {
    submit() {
      console.log(this.selectedClub)
    }
  },
}
</script>
