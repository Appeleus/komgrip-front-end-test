<script setup>

import { CContainer } from '@coreui/vue';
import { ref, computed } from 'vue'

// Either Green or Red Depends on the last result
// if it's more than or less than the current changePercent24Hr.
const PercentColor = computed(() => {
    return '#81d514'
})
const CardCurrentColor = computed(() => {
    return 'white'
})
const GrayTextColor = computed(() => {
    return 'gray';
})
const NavyBlueColor = computed(() => {
    return '#2b3f61';
})

const props = defineProps({
    name: String,
    priceUsd: String,
    changePercent24Hr: String
})
</script>

<template>
    <CContainer fluid>

        <UCard :ui="{
            background: 'bg-white dark:bg-gray-900',
            rounded: 'rounded-lg',
            shadow: 'md',
            body: { padding: 'p-3' }
        }">
            <CRow class="d-flex">
                <CCol class="col-8" :style="{ fontWeight: 'bold' }">
                    <h2 :style="{ color: GrayTextColor, fontSize: '14px' }">{{ name }}</h2>
                    <h1 :style="{ color: NavyBlueColor, fontSize: '20px' }">{{ (priceUsd.substring(0,10)) }}</h1>
                    <h2 :style="{ color: PercentColor, fontSize: '14px' }">{{ changePercent24Hr.substring(0,5) }}%</h2>
                </CCol>
                <CCol class="col-4 justify-content-end d-flex">
                    <div class="gradient-square ">
                        <UIcon name="i-material-symbols-light:database" :style="{ width: '18px', height: '18px' }" />
                    </div>
                </CCol>
            </CRow>
        </UCard>

    </CContainer>
</template>

<style>
.gradient-square {
    background-image: linear-gradient(310deg, #7928ca, #ff0080);
    width: 48px;
    height: 48px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 0.5rem;
}
.gradient-square span {
    color: white;
}
</style>
