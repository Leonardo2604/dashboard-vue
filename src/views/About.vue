<template>
    <div class="about">
        <h1>This is an about page</h1>
        <div class="Chart">
          <h2>Linechart</h2>
          <sg-line :chartdata="chartdata" :options="options"></sg-line>
        </div>
         <div class="Chart">
          <h2>Barchart</h2>
          <sg-bar :chartdata="chartdata" :options="options"></sg-bar>
        </div>
        <div>

        </div>
    </div>
</template>

<script>
    import SgLine from '../components/chart/SgLine.vue';
    import SgBar from '../components/chart/SgBar.vue';


    export default {
        name: 'About',
        components: {
            SgLine,
            SgBar
        },
        data: function() {
            return {
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
                options: {
                    responsive: true,
                    maintainAspectRatio: false
                }
            }
        }
    };
</script>

<style>
.Chart {
  background: #212733;
  border-radius: 15px;
  box-shadow: 0px 2px 15px rgba(25, 25, 25, 0.27);
  margin:  25px 0;
}

.Chart h2 {
  margin-top: 0;
  padding: 15px 0;
  color:  rgba(255, 0,0, 0.5);
  border-bottom: 1px solid #323d54;
}
</style>

