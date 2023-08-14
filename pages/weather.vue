<!-- eslint-disable vue/v-slot-style -->
<template>
    <div>
      <v-card class="pa-3 mx-auto" flat color="transparent">
        <v-card-title> Weather </v-card-title>
        <!-- Filters Section -->
        <v-card-text>
          <v-row>
            <v-col cols="12" md="4">
              <v-autocomplete
                :items="items"
                dense
                label="Country"
                hide-details="auto"
              />
            </v-col>
            <v-col cols="12" md="4">
              <v-autocomplete
                :items="city"
                dense
                label="City"
                hide-details="auto"
              />
            </v-col>
            <v-col cols="12" md="4">
              <v-btn icon color="primary" @click="dialog = true"
                ><v-icon>mdi-calendar-clock</v-icon></v-btn
              ><span class="ml-3 blue--text">{{ displayPicker }}</span>
              
            </v-col>
            <v-col>
              <v-dialog v-model="dialog" max-width="290">
                <v-card>
                  <v-card-text>
                    <v-row justify="center">
                      <v-date-picker v-model="picker"></v-date-picker>
                    </v-row>
                  </v-card-text>
                  <v-card-actions>
                    <v-spacer />
                    <v-btn color="red darken-1" text @click="dialog = false">
                      Cancel
                    </v-btn>
                    <v-btn color="primary" text @click="onClose"> OK </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-col>
          </v-row>
        </v-card-text>
        <!-- Display Section -->
        <v-card-text>
          <v-card max-width="350" class="pa-5">
            <v-card-actions>
              <div>
                <div class="text-caption grey--text">Day</div>
                <div class="font-weight-bold grey--text text--darken-2">
                  Today
                </div>
              </div>
              <v-spacer />
              <div>
                <div class="text-caption grey--text">Status</div>
                <div class="font-weight-bold grey--text text--darken-2">
                  Sunny
                </div>
              </div>
            </v-card-actions>
            <v-card-text>
              <div class="text-center">
                <v-icon color="yellow darken-1" class="text-h1"
                  >mdi-white-balance-sunny</v-icon
                >
              </div>
              <div class="text-center text-h5">Vientiane</div>
              <div class="text--darken-2 text-center text-h1 mt-3">25°</div>
            </v-card-text>
            <v-card-text>
              <div>Windy: 23km/h</div>
              <div>09:54 <span class="pl-10">23°</span></div>
              <div>10:37 <span class="pl-10">23°</span></div>
              <div>11:40 <span class="pl-10">23°</span></div>
            </v-card-text>
            <v-expansion-panels flat>
              <v-expansion-panel>
                <v-expansion-panel-header> Show More </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-simple-table dense>
                    <template v-slot:default>
                      <tbody>
                        <tr v-for="item in desserts" :key="item.hour">
                          <td>{{ item.hour }}</td>
                          <td>{{ item.temperature }}</td>
                        </tr>
                      </tbody>
                    </template>
                  </v-simple-table>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-card>
        </v-card-text>
      </v-card>
    </div>
  </template>
  <script>
  export default {
    data: () => ({
      items: ["Laos", "Thailand", "China", "Vietnam"],
      city: ["Vientiane", "Bolikhamxay", "Vangvieng"],
      desserts: [
        {
          hour: "11:40",
          temperature: "23°",
        },
        {
          hour: "11:40",
          temperature: "23°",
        },
        {
          hour: "11:40",
          temperature: "23°",
        },
        {
          hour: "11:40",
          temperature: "23°",
        },
      ],
      dialog: false,
      picker: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
        .toISOString()
        .substr(0, 10),
      displayPicker: null,
    }),
    methods: {
      onClose() {
        this.dialog = false
        this.displayPicker = this.picker
      },
    },
  };
  </script>
  