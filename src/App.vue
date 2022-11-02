<template>
  <v-app>
    <v-main>
      <ContentBlock/>
    </v-main>

    <v-footer app v-bind="localAttrs">
      <XFooter />
    </v-footer>
  </v-app>
</template>
<script lang="ts">
import { defineComponent, computed } from 'vue'
import ContentBlock from '@/components/ContentBlock.vue';
import XFooter from '@/components/XFooter.vue';

export default defineComponent({
  name: 'App',
  components: {
    ContentBlock,
    XFooter,
  },
  setup() {
    const localAttrs = computed(() => {
      const attrs = {
        absolute: false,
        fixed: false
      }

      attrs.absolute = true
      attrs.fixed = false

      return attrs
    });
    return {
      localAttrs
    }
  },
})
</script>
