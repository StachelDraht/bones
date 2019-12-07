<template>
    <div>
        <div>
            <v-text-field
                label="Solo"
                placeholder="Placeholder"
                solo
            ></v-text-field>
        </div>
        <input type="text" name="r" placeholder="r" v-model="r" />
        <input type="tex" name="B" placeholder="L" v-model="l" />
        <div>
            Best fit circle glenoid area (A) = &#928;(r)<sup>2</sup> = {{ valueA }}
        </div>
        <div>
            Area of bone loss (B) = r<sup>2</sup> / 2 (&#928; / 180 * L - sin L) = {{ valueB }}
        </div>
        <div>
            Percentage bone loss: B/A * 100% = {{ valueResult }}
        </div>
    </div>
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
            return Math.PI*(Math.pow(this.r, 2))
        },
        valueB: function() {
            let a = Math.pow(this.r,2) / 2
            let sin = (Math.sin(this.l*Math.PI/180))
            return a * (Math.PI / 180 * this.l - sin) //r2 / 2 (Π / 180 * L - sin L) 
        },
        valueResult: function() {
            return (this.valueB/this.valueA) * 100
        }
    }
}
</script>