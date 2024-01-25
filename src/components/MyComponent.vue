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
     title:  'Juan Perez 1',
      id: 'DAF',
     disabled: false,
    },
      {
      title:  'Juana de Arco',
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
    this.itemsSelected = {title: null, id: null};
  },
  methods: {
    submit() {
      console.log(this.selectedClub)
    }
  },
}
</script>
