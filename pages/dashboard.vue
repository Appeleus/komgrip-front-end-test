<script setup>
import '@coreui/coreui/dist/css/coreui.min.css'
import 'bootstrap/dist/css/bootstrap.min.css'
import axios from "axios";
import { ref, onMounted } from 'vue';

definePageMeta({
    layout: 'default'
});

const currencyData = ref([]);

onMounted(async () => {
    try {
        const response = await axios.get('https://komgrip.co.th/coincap/assets');
        currencyData.value = response.data.data;
    } catch (err) {
        console.log("Api called failed :(")
        throw err
    }
});

</script>

<template>
    <div>
        <CRow class="d-flex">
            <CCol v-for="crypto in currencyData.slice(0, 4)" :key="crypto.id">
                <Card :name="crypto.name" :price-usd="crypto.priceUsd" :change-percent24-hr="crypto.changePercent24Hr" />
            </CCol>
        </CRow>
        <CRow style="padding: 20px">
            <InfoTable :data="currencyData" />
        </CRow>

    </div>
</template>
