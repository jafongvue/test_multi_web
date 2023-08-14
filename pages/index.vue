<!-- eslint-disable vue/singleline-html-element-content-newline -->
<template>
  <div>
    <v-card flat color="transparent">
      <v-card-text>
        <v-row class="mt-5" align="center">
          <v-col cols="10" md="6">
            <v-text-field
              placeholder="Please enter a word"
              dense
              outlined
              hide-details="auto"
            />
          </v-col>
          <v-col cols="2">
            <v-btn icon><v-icon>mdi-magnify</v-icon></v-btn>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" sm="4" md="6">
            <div>
              <v-card class="pa-3">
                <div class="text--subtitle-4 text--disabled">How to read</div>
                <div class="text-h5">
                  [ lawng, {{ $route.query.word || "long" }} ]
                  <v-btn icon>
                    <v-icon>mdi-volume-high</v-icon>
                  </v-btn>
                </div>
              </v-card>
            </div>
          </v-col>
        </v-row>
        <div>
          <v-row>
            <v-col v-for="i in 5" :key="i" cols="12" md="4">
              <v-card width="400" min-height="300" elevation="1">
                <v-card-title>
                  Defination #{{ i }}
                  <v-spacer />
                  <v-chip label small>Noun</v-chip>
                </v-card-title>
                <v-card-subtitle>
                  See synonyms for long on Thesaurus.com
                </v-card-subtitle>
                <v-card-text>
                  <v-divider />

                  <div class="mt-3">a comparatively long time:</div>
                  <div>They haven't been gone for long. Will it take long?</div>
                  <div class="mt-3">something that is long:</div>
                  <div>The signal was two longs and a short.</div>
                  <div class="mt-10 d-flex">
                    <div
                      class="text-decoration-underline"
                      @click="$router.push('?word=far')"
                    >
                      Far,
                    </div>
                    <div
                      class="text-decoration-underline pl-1"
                      @click="$router.push('?word=time')"
                    >
                      Time
                    </div>
                  </div>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {};
</script>
