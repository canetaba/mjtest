<template>
  <div>
    <v-select
        :items="items"
        density="comfortable"
        label="Escoja el visador"
    ></v-select>

    <v-select
        :items="items"
        density="comfortable"
        label="Escoja el firmante"
    ></v-select>
  </div>


  <div>
    <v-app>
      <v-container>
        <v-select
            :items="items"
            v-model="itemsSelected"
            item-title="title"
            item-value="id"
            multiple
        >
          <template v-slot:item="{ props, item }">
            <v-list-item
                v-bind="props"
                :subtitle="item.raw.department"
                :disabled="item.raw.disabled"
            ></v-list-item>
          </template>
        </v-select>
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
     title:  'Opción 1',
      id: 442,
     disabled: false,
    }, {
      title:  'Opción 2',
      id: 443,
      disabled: true,
    },
      {
        title:  'Opción 3',
        id: 444,
        disabled: false,
      }
    ],


  }),
}
</script>
