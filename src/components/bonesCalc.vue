<template>
  <v-app id="inspire">
    <v-content>
      <v-container
        class="fill-height"
        fluid
      >
        <v-row
          align="center"
          justify="center"
        >
          <v-col
            cols="12"
            sm="8"
            md="4"
          >
            <v-card class="elevation-12">
            <v-img src="bone.png"></v-img>
              <v-card-text>
                  <v-text-field
                    label="r"
                    name="r"
                    type="text"
                    v-model="r"
                  />

                  <v-text-field
                    label="L"
                    name="l"
                    type="text"
                    v-model="l"
                  />
              </v-card-text>
              <v-card-text>Best fit circle glenoid area (A) = &#928;(r)<sup>2</sup> = {{ valueA }}</v-card-text>
              <v-card-text>Area of bone loss (B) = r<sup>2</sup> / 2 (&#928; / 180 * L - sin L) = {{ valueB }}</v-card-text>
              <v-card-text>Percentage bone loss: B/A * 100% = <b v-if="valueResult != 'NaN'">{{ valueResult }}</b></v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>
<script>
export default {
    data: function() {
        return {
            l : '',
            r : ''
        }
    },
    computed: {
        valueA: function() {
            let result = Math.PI*(Math.pow(this.r, 2))
            return result.toFixed(3)
        },
        valueB: function() {
            let a = Math.pow(this.r,2) / 2
            let sin = (Math.sin(this.l*Math.PI/180))
            let result =  a * (Math.PI / 180 * this.l - sin) //r2 / 2 (Π / 180 * L - sin L) 
            return result.toFixed(3)
        },
        valueResult: function() {
            let result = (this.valueB/this.valueA) * 100
            return result.toFixed(3)
        }
    }
}
</script>