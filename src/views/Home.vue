<template>
    <v-container fluid grid-list-xl style="padding: 13px">
        <v-layout column>
            <v-layout row wrap>
                <v-flex xs12 sm6 xl3>
                   <indicator-card :current="10" :last="12" title="Reclamações"/>
                </v-flex>

                <v-flex xs12 sm6 xl3>
                   <indicator-card :current="21" :last="12" title="Produtos Vendidos"/>
                </v-flex>

                <v-flex xs12 sm6 xl3>
                   <indicator-card :current="21" :last="21" title="Ordens de Serviços Abertas"/>
                </v-flex>

                <v-flex xs12 sm6 xl3>
                   <indicator-card :current="34" :last="32" title="Orderns de Serviço Concluidas"/>
                </v-flex>
            </v-layout>
            <v-layout row wrap>
                <v-flex xs12 md6 xl9>
                    <v-card height="450">
                        <v-card-text>Leonardo</v-card-text>
                    </v-card>
                </v-flex>

                <v-flex xs12 md6 xl3>
                    <v-card height="450">
                        <v-card-text>Leonardo</v-card-text>
                    </v-card>
                </v-flex>
            </v-layout>
            <v-layout row wrap>
                <v-flex xs12 md6>
                    <v-card height="450">
                        <v-card-text>Leonardo</v-card-text>
                    </v-card>
                </v-flex>
                <v-flex xs12 md6>
                    <v-card height="450">
                        <v-card-text>Leonardo</v-card-text>
                    </v-card>
                </v-flex>
            </v-layout>
            <v-layout row wrap>
                <v-flex xs12>
                    <v-card height="450">
                        <v-card-text>Leonardo</v-card-text>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-layout>
    </v-container>
</template>

<script>
    import IndicatorCard from "../components/IndicatorCard.vue";

    export default {
        components: {
            IndicatorCard
        },
        data: function () {
            return {
                lightValue: 100,
                teste: ('ondevicelight' in window) ? 'SIM' : 'NÃO',
                teste2: (window.AmbientLightSensor) ? 'SIM' : 'NÃO'
            };
        }
    }
</script>