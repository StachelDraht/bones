<template>
  <v-app>
    <v-content>
      <bonesCalc />
    </v-content>
  </v-app>
</template>

<script>
import bonesCalc from './components/bonesCalc'

export default {
  name: 'App',

  components: {
    bonesCalc
  },

  data: () => ({
    //
  }),
};
</script>
