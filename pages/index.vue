<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-row justify="space-around">
      <v-switch
        class="mx-5"
        v-model="tab"
        label="タブかどうか"
        color="primary"
      />
      <v-switch
        class="mx-5"
        v-model="visibilitySelected"
        label="選択済みを表示するかどうか"
        color="primary"
      />
      <v-switch
        class="mx-5"
        v-model="upper"
        :label="`上部か下部か : ${upper === true ? '上部' : '下部'}`"
        :disabled="visibilitySelected === false"
        color="primary"
      />
    </v-row>
    <business-kind-modal
      :isTab="tab"
      :isVisibleSelected="visibilitySelected"
      :isUpper="upper"
    />    
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import BusinessKindModal from '~/components/BusinessKindModal.vue'

export default {
  components: {
    Logo,
    VuetifyLogo,
    BusinessKindModal
  },
  data() {
    return {
      tab: true,
      visibilitySelected: false,
      upper: true
    }
  }
}
</script>
