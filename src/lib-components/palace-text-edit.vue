<template>
  <div>
    <label>{{ label }}</label>
    <v-text-field v-bind="{ ...$attrs, ...commonAttrs }" v-on="$listeners">
      <template
        v-for="(_, scopedSlotName) in $scopedSlots"
        #[scopedSlotName]="slotData"
      >
        <slot :name="scopedSlotName" v-bind="slotData" />
      </template>
      <template v-for="(_, slotName) in $slots" #[slotName]>
        <slot :name="slotName" />
      </template>
    </v-text-field>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'PalaceTextEdit', // vue component name
  inheritAttrs: false,
  props: {
    label: {
      type: String,
      default: "",
    },
  },
  computed: {
    commonAttrs() {
      return {
        label: "",
        persistentHint: true,
        outlined: true,
        dense: true,
        hideDetails: false,
      };
    },
  },
});
</script>
