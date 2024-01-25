<template>
   <div>
    <v-app>
      <v-container>
        <v-autocomplete
            :items="items"
            density="comfortable"
            label="Escoja el firmante"
            v-model="itemsSelected"
            item-title="title"
            item-value="id"
            multiple
        >
          <template v-slot:item="{ props, item }">
            <v-list-item
                v-bind="props"
                :subtitle="item.raw.id"
                :disabled="item.raw.disabled"
            ></v-list-item>
          </template>
        </v-autocomplete>
      </v-container>
    </v-app>
  </div>
</template>

<script>
export default {
  name:  'MyComponente',
  data: () => (
      {
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


  }),
}
</script>
