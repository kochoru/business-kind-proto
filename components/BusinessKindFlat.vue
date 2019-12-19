<template>
  <v-row
    no-gutters>
    <v-col
      cols=4
    >
      <div
        class="my-5 index-title"
      >
        <v-icon left>mdi-excavator</v-icon>
        {{ businessKinds[0]['name'] }}
      </div>
      <div
        class="my-5 index-title"
      >
        <v-icon left>mdi-office-building</v-icon>
        {{ businessKinds[1]['name'] }}
      </div>
      <div
        class="my-5 index-title"
      >
        <v-icon left>mdi-hospital-box</v-icon>
        {{ businessKinds[2]['name'] }}
      </div>
      <div
        class="my-5 index-title"
      >
        <v-icon left>mdi-silverware-variant</v-icon>
        {{ businessKinds[3]['name'] }}
      </div>
    </v-col>
    <v-col
      cols=8
    >
      <v-card flat>
        <v-card-text>
          <v-row justify="space-around">
            <v-checkbox
              v-model="selected"
              v-for="child of businessKinds[0]['children']"
              color="primary"
              :key="child['id']"
              :label="child['name']"
              :value="child['name']"
              class="my-0"
              @change="checkBoxChanged"
            />
          </v-row>
          <v-divider />
          <v-row justify="space-around" class="mt-8">
            <v-checkbox
              v-model="selected"
              v-for="child of businessKinds[1]['children']"
              color="primary"
              :key="child['id']"
              :label="child['name']"
              :value="child['name']"
              class="my-0"
              @change="checkBoxChanged"
            />
          </v-row>
          <v-divider />
          <v-row justify="space-around" class="mt-8">
            <v-checkbox
              v-model="selected"
              v-for="child of businessKinds[2]['children']"
              color="primary"
              :key="child['id']"
              :label="child['name']"
              :value="child['name']"
              class="my-0"
              @change="checkBoxChanged"
            />
          </v-row>
          <v-divider />
          <v-row justify="space-around" class="mt-8">
            <v-checkbox
              v-model="selected"
              v-for="child of businessKinds[3]['children']"
              color="primary"
              :key="child['id']"
              :label="child['name']"
              :value="child['name']"
              class="my-0"
              @change="checkBoxChanged"
            />
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>

  </v-row>
</template>

<script>
import BusinessKinds from '~/const/business-kind'

export default {
  data() {
    return {
      selected: [],
      businessKinds: BusinessKinds,
    }
  },
  methods: {
    checkBoxChanged: function() {
      this.$emit("change", this.selected)
    }
  }
}
</script>

<style>
.index-title {
  text-align: center;
}
</style>