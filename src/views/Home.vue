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
                <v-flex xs12 xl6 >
                    <v-card height="450" pa-3>
                        <sg-line :chartdata="chartdata" :options="options"></sg-line>
                    </v-card>
                </v-flex>

                <v-flex xs12 xl6 >
                    <!-- <v-card height="450"> -->
                        <v-data-table
                            :headers="headers"
                            :items="desserts"
                            class="elevation-1"
                        >
                            <template v-slot:items="props">
                            <td>{{ props.item.name }}</td>
                            <td>{{ props.item.quantity }}</td>
                            <td>{{ props.item.min_quantity }}</td>
                            </template>
                        </v-data-table>
                    <!-- </v-card> -->
                </v-flex>
            </v-layout>
            <v-layout row wrap>
                <v-flex xs12 md6>
                    <v-card height="450">
                        <v-card-text>
                            <sg-pie :chartdata="pie" :options="options"></sg-pie>
                        </v-card-text>
                    </v-card>
                </v-flex>
                <v-flex xs12 md6>
                    <v-data-table
                            :headers="headers"
                            :items="desserts"
                            class="elevation-1"
                        >
                            <template v-slot:items="props">
                            <td>{{ props.item.name }}</td>
                            <td>{{ props.item.quantity }}</td>
                            <td>{{ props.item.min_quantity }}</td>
                            </template>
                        </v-data-table>
                </v-flex>
            </v-layout>
            <v-layout row wrap>
                <v-flex xs12>
                    <v-card height="450">
                        <v-card-text>
                            <sg-bar :chartdata="chartdata" :options="options"></sg-bar>
                        </v-card-text>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-layout>
    </v-container>
</template>

<script>
    import IndicatorCard from "../components/IndicatorCard.vue";
    import SgLine from '../components/chart/SgLine.vue';
    import SgPie from '../components/chart/SgPie.vue';
    import SgBar from '../components/chart/SgBar.vue';

    export default {
        components: {
            IndicatorCard,
            SgLine,
            SgPie,
            SgBar
        },
        data: function () {
            return {
                headers: [
                    { text: 'Nome', value: 'name' },
                    { text: 'Quant.', value: 'quantity' },
                    { text: 'Min Quant', value: 'min_quantity' }
                ],
                desserts: [
                    {
                        name: 'Camiseta Regata',
                        quantity: 159,
                        min_quantity: 6.0
                    },
                    {
                        name: 'Ice cream sandwich',
                        quantity: 237,
                        min_quantity: 9.0
                    },
                    {
                        name: 'Eclair',
                        quantity: 262,
                        min_quantity: 16.0
                    },
                    {
                        name: 'Cupcake',
                        quantity: 305,
                        min_quantity: 3.7
                    },
                    {
                        name: 'Gingerbread',
                        quantity: 356,
                        min_quantity: 16.0
                    },
                    {
                        name: 'Jelly bean',
                        quantity: 375,
                        min_quantity: 0.0
                    },
                    {
                        name: 'Lollipop',
                        quantity: 392,
                        min_quantity: 0.2
                    },
                    {
                        name: 'Honeycomb',
                        quantity: 408,
                        min_quantity: 3.2
                    },
                    {
                        name: 'Donut',
                        quantity: 452,
                        min_quantity: 25.0
                    },
                    {
                        name: 'KitKat',
                        quantity: 518,
                        min_quantity: 26.0
                    }
                ],
                chartdata: {
                    labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
                    datasets: [
                        {
                            label: 'Data One',
                            borderColor: '#FC2525',
                            pointBackgroundColor: 'white',
                            borderWidth: 1,
                            pointBorderColor: 'white',
                            backgroundColor: this.gradient,
                            data: [40, 39, 10, 40, 39, 80, 40]
                        },{
                            label: 'Data Two',
                            borderColor: '#05CBE1',
                            pointBackgroundColor: 'white',
                            pointBorderColor: 'white',
                            borderWidth: 1,
                            backgroundColor: this.gradient2,
                            data: [60, 55, 32, 10, 2, 12, 53]
                        }
                    ]
                },
                pie: {
                    labels: ['teste1', 'teste2'],
                    datasets: [
                        {
                            backgroundColor: ['#cecece', '#05CBE1'],
                            data: [40, 29]
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false
                }
            }
        }
    }
</script>