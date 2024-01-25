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
</template>

<script>
export default {
  name:  'MyComponente',
  data: () => ({
    items: ['Opción 1', 'Opción 2', 'Opción 3', 'Opción 4'],
  }),
}
</script>
