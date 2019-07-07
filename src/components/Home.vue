<template>
  <v-app dark="">
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant.sync="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar :clipped-left="clipped" dark="" fixed app>
      <v-toolbar-side-icon @click="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>{{ miniVariant ? "chevron_right" : "chevron_left" }}</v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>remove</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>

    <v-content>
      <h1>Ranking Produtos mais Vendidos</h1>
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

      <nuxt />
    </v-content>

    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: "bubble_chart",
          title: "Previsibilidade",
          to: "/previsibilidade"
        },
        {
          icon: "store",
          title: "Compras",
          to: "/compras"
        },
        {
          icon: "apps",
          title: "Sair",
          to: "/"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Dashboard",

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
