<template>
    <v-card height="350" class="pa-3" style="flex-direction: column">
        <h2>{{ title }}</h2>
        <v-tabs grow>
            <v-tab ripple>Indicador</v-tab>
            <v-tab ripple>Gráfico</v-tab>

            <v-tab-item>
                <v-card flat class="pt-3">
                    <div class="text-xs-right">
                        Ultimo Mês: {{ last }}
                    </div>
                    <div class="text-xs-center d-flex align-center">
                        <h2>{{ `${percentage} %` }}</h2>
                        <v-icon color="success" size="110" v-show="current > last">arrow_drop_up</v-icon>
                        <v-icon color="yellow" size="110" v-show="current == last">remove</v-icon>
                        <v-icon color="red" size="110" v-show="current < last">arrow_drop_down</v-icon>
                    </div>
                    <div class="d-flex text-xs-right align-end">
                        <span>Atual Mês: {{ current }}</span>
                    </div>
                </v-card>
            </v-tab-item>

            <v-tab-item>
                <v-card flat class="pt-3">

                </v-card>
            </v-tab-item>
        </v-tabs>
    </v-card>
</template>

<script>
    export default {
        name: 'IndicatorCard',
        props: {
            title: {
                type: String,
                required: true
            },
            current: {
                type: Number,
                required: true,
            },
            last: {
                type: Number,
                required: true,
            }
        },
        components: {

        },
        data: function() {
            return {

            }
        },
        computed: {
            percentage: function() {
                return (((this.current * 100) /  this.last) - 100).toPrecision(4);
            }
        },
        methods: {

        }
    }
</script>


