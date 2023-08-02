<template>
    <div class="dashboard">
        <div class="row">
            <div class="col-12 p-3">
                <Line :data="monthlyConnectionsData" :options="options" class="bg-white" />
            </div>
            <div class="col-12 col-md-6">
                <Doughnut :data="osUsersData" :options="options" class="bg-white" />
            </div>
            <div class="col-12 col-md-6">
                <Bar :data="usersAgeRangeData" :options="options" class="bg-white" />
            </div>
        </div>
    </div>
</template>
  
  

<script>
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale, DoughnutController, ArcElement, PointElement, LineElement } from 'chart.js';
import { Bar, Doughnut, Line } from 'vue-chartjs';
import { monthlyConnections, usersAgeRange, devices } from '../data/data.js';

ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend, DoughnutController, ArcElement, PointElement, LineElement);

export default {
    name: 'ChartComp',
    components: {
        Bar,
        Doughnut,
        Line
    },
    data() {
        return {
            monthlyConnectionsData: null,
            osUsersData: null,
            usersAgeRangeData: null,
            options: {
                responsive: true,
            },
        };
    },
    created() {
        ChartJS.register(DoughnutController);
        this.processData();
    },
    methods: {
        processData() {
            // Process data for each chart
            this.monthlyConnectionsData = {
                labels: monthlyConnections.map(entry => entry.month),
                datasets: [{
                    label: 'Connessioni mensili',
                    data: monthlyConnections.map(entry => entry.connections),
                    backgroundColor: 'rgba(75, 192, 192, 0.7)',
                    borderWidth: 1,
                }],
            };

            this.osUsersData = {
                labels: devices.map(entry => entry.os),
                datasets: [{
                    data: devices.map(entry => entry.connections),
                    backgroundColor: [
                        'rgba(255, 99, 132, 0.7)',
                        'rgba(54, 162, 235, 0.7)',
                        'rgba(255, 206, 86, 0.7)',
                        'rgba(75, 192, 192, 0.7)',
                        'rgba(153, 102, 255, 0.7)',
                    ],
                    borderWidth: 1,
                }],
            };

            this.usersAgeRangeData = {
                labels: usersAgeRange.map(entry => entry.range),
                datasets: [{
                    label: 'Connessioni per range di età',
                    data: usersAgeRange.map(entry => entry.connections),
                    backgroundColor: 'rgba(75, 192, 192, 0.7)',
                    borderWidth: 1,
                }],
            };
        },
    },
};
</script>

<style lang="scss" scoped></style>
