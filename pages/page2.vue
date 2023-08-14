<template>
  <v-data-table
    :items-per-page="3"
    :headers="headers"
    :items="desserts"
    :footer-props="{
      'items-per-page-text': 'test',
      'items-per-page-options': [10, 20, 60, 100],
      'prev-icon': 'mdi-heart',
      'next-icon': 'mdi-heart',
    }"
    class="elevation-1"
    >
    <template #[`item.iron`]="{item}">
      <v-img
        :src="item.iron"
        width="100"
      ></v-img>
    </template>
  </v-data-table>
</template>
<script>
export default {
  data() {
    return {
      headers: [
        {
          text: 'Name',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Num1', value: 'calories' },
        { text: 'Num2', value: 'fat' },
        { text: 'Num3', value: 'carbs' },
        { text: 'Num4', value: 'protein' },
        { text: 'Picture', value: 'iron' },
      ],
      desserts: [
        {
          name: 'JeeVang',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: 'https://images.unsplash.com/photo-1533450718592-29d45635f0a9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MXx8anBnfGVufDB8fDB8fA%3D%3D&w=1000&q=80',
        },
        {
          name: 'Jafong',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: 'https://images.unsplash.com/photo-1598970829637-89b81d47ae27?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80',
        },
        {
          name: 'Veexiong',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQA4ElsjILxY6_Dji3p5IVb02d7fjuUeEi52Nj9dcjWkRBAl6k8hw0DJ_Un1uAsx2z66ko&usqp=CAU',
        },
      ],
    }
  },
}
</script>
