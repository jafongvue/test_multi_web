<!-- eslint-disable vue/v-slot-style -->
<!-- eslint-disable vue/no-v-text-v-html-on-component -->
<template>
  <v-card>
    <v-tabs v-model="tab">
      <v-tabs-slider color="orange"></v-tabs-slider>
      <v-tab v-for="item in 4" :key="item">
       Menu {{ item }}
      </v-tab>
    </v-tabs>
    <v-tabs-items v-model="tab">
      <v-tab-item>
        <v-card flat>
          <v-card-text>1</v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>2</v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>3</v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>3</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      tab: null,
      items: ['Home', 'shopping', 'videos', 'images', 'news'],
      text: 'Hello',
    }
  },
}
</script>
