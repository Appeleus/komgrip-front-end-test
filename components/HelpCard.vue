<script setup>

import { CContainer } from '@coreui/vue';
import { ref, computed } from 'vue'

// Either Green or Red Depends on the last result
// if it's more than or less than the current changePercent24Hr.

const props = defineProps({
    name: String,
    priceUsd: String,
    changePercent24Hr: String
})
</script>

<template>
    <CContainer>
        <CCol>
            <UCard :ui="{
                shadow: 'md',
                body: { padding: 'p-3', background: 'silver-background' }
            }">
                <CRow>
                    <CCol>
                        <h5>Need help?</h5>
                        CoinCap API 2.0
                    </CCol>
                </CRow>
                <CRow>
                    <CCol>
                        <UButton :style="{ color: 'black' }" block color="white" variant="solid">DOCUMENTATION</UButton>
                    </CCol>
                </CRow>
            </UCard>
        </CCol>
    </CContainer>
</template>

<style>
.silver-background {
    background-image: url("../assets/img/white-curved.jpeg");
    border-radius: 10px;
    width: auto;
}

.black-text {
    color: black;
}
</style>
