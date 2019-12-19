<template>
  <v-tabs vertical>
    <v-tab>
      <v-icon left>mdi-excavator</v-icon>
      {{ businessKinds[0]['name'] }}
    </v-tab>
    <v-tab>
      <v-icon left>mdi-office-building</v-icon>
      {{ businessKinds[1]['name'] }}
    </v-tab>
    <v-tab>
      <v-icon left>mdi-hospital-box</v-icon>
      {{ businessKinds[2]['name'] }}
    </v-tab>
    <v-tab>
      <v-icon left>mdi-silverware-variant</v-icon>
      {{ businessKinds[3]['name'] }}
    </v-tab>

    <v-tab-item>
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
        </v-card-text>
      </v-card>
    </v-tab-item>
    <v-tab-item>
      <v-card flat>
        <v-card-text>
          <v-row justify="space-around">
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
        </v-card-text>
      </v-card>
    </v-tab-item>
    <v-tab-item>
      <v-card flat>
        <v-card-text>
          <v-row justify="space-around">
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
        </v-card-text>
      </v-card>
    </v-tab-item>
    <v-tab-item>
      <v-card flat>
        <v-card-text>
          <v-row justify="space-around">
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
    </v-tab-item>
  </v-tabs>
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

</style>