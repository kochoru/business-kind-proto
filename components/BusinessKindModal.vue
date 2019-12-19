<template>
  <v-dialog
    v-model="dialogVisible"
    width="800"
    scrollable
  >
    <template v-slot:activator="{ on }">
      <v-btn
        v-on="on"
        color="primary"
      >
        <!-- <v-row v-if="selected.length !== 0">
          <v-chip
            v-for="item of selected"
            :key="item"
            light
            close
            class="ma-1 position-fixed"
            @click:close="closeSelected"
          >
            {{ item }}
          </v-chip>
        </v-row> -->
        業種を選ぶ
      </v-btn>
    </template>

    <v-card>
      <v-card-title>
        <v-row>
          <v-col
            cols="2">
            業種を選ぶ
          </v-col>
          <v-col
            cols="10">
            <template
              v-if="isUpper && isVisibleSelected"
            >
              <v-row>
                <v-chip
                  v-for="item of selected"
                  :key="item"
                  light
                  close
                  class="ma-1 position-fixed"
                  @click:close="closeSelected"
                >
                  {{ item }}
                </v-chip>
              </v-row>
            </template>
          </v-col>
        </v-row>
      </v-card-title>
      
      <v-divider></v-divider>

      <v-card-text style="height: 600px;" class="mx-0 px-0">
        <business-kind-tab
          v-if="isTab"
          @change="handleChange"
        />
        <business-kind-flat
          v-else
          @change="handleChange"
        />
      </v-card-text>

      <v-divider></v-divider>

      <v-card-actions>
        <template
          v-if="!isUpper && isVisibleSelected"
        >
          <v-row>
            <v-chip
              v-for="item of selected"
              :key="item"
              light
              close
              class="ma-1 position-fixed"
              @click:close="closeSelected"
            >
              {{ item }}
            </v-chip>
          </v-row>
        </template>
        <v-spacer></v-spacer>
        <v-btn
          color="primary"
          text
          @click="dialogVisible = false"
        >
          完了
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
import BusinessKinds from '~/const/business-kind'
import BusinessKindTab from '~/components/BusinessKindTab.vue'
import BusinessKindFlat from '~/components/BusinessKindFlat.vue'


export default {
  components: {
    BusinessKindTab,
    BusinessKindFlat,
  },
  props: {
    isTab: Boolean,
    isVisibleSelected: Boolean,
    isUpper: Boolean
  },
  data() {
    return {
      dialogVisible: true,
      businessKinds: BusinessKinds,
      selected: []
    }
  },
  methods: {
    handleChange: function(selected) {
      console.log(this.selected)
      this.selected = selected
    },
    closeSelected: function(closed) {
      this.selected.pop(closed)
    },
  }
}
</script>

<style>
</style>