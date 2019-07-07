<template>
  <div>
    <h1>Previsibilidade de Compras</h1>
    <br />
    <br />

    <v-data-table :headers="headers" :items="desserts" class="elevation-1">
      <template v-slot:items="props">
        <td>{{ props.item.name }}</td>
        <td class="text-xs-right">{{ props.item.calories }}</td>
        <td class="text-xs-right">{{ props.item.fat }}</td>
        <td class="text-xs-right">{{ props.item.carbs }}</td>
        <td class="text-xs-right">{{ props.item.protein }}</td>
        <td class="text-xs-right">{{ props.item.iron }}</td>
      </template>
    </v-data-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "Produto",
          align: "left",
          sortable: false,
          value: "name"
        },
        { text: "Quantidade", value: "calories" }
      ],
      desserts: [
        {
          name: "Coca-cola",
          calories: 159
        },
        {
          name: "Cerveja Heineken",
          calories: 503
        },
        {
          name: "Carvão para assar",
          calories: 30
        },
        {
          name: "Gelo",
          calories: 33
        },
        {
          name: "Kit Kat",
          calories: 50
        },
        {
          name: "Sorvete Marta Rocha",
          calories: 113
        },
        {
          name: "Mamão",
          calories: 30
        },
        {
          name: "Cerveja Kaiser",
          calories: 895
        },
        {
          name: "Torta de Queijo",
          calories: 20
        },
        {
          name: "Farofa",
          calories: 13
        },
        {
          name: "Fraldas",
          calories: 650
        }
      ]
    };
  }
};
</script>
