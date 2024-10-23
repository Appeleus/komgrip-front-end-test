<script setup>

import { CContainer } from '@coreui/vue';
import { ref, computed, watch } from 'vue'
const props = defineProps({
    data: Array
})

const data = computed(() => {
    return props.data.map(item => ({
        rank: item.rank,
        name: item.name,
        symbol: item.symbol,
        supply: item.supply,
        maxSupply: item.maxSupply,
        priceUsd: item.priceUsd,
        vwap24Hr: item.vwap24Hr
    })
    )
})

const slicedList = computed(() => {
    const value = data.value
    return value.slice((page.value - 1) * listPerPage, (page.value * listPerPage))
})

const page = ref(1)
const listPerPage = 5;

const Pinkish = computed(() => {
    return '#ff0080';
})

</script>

<template>
    <CContainer fluid>
        <UCard :ui="{
            background: 'bg-white',
            rounded: 'rounded-lg',
            shadow: 'md',
            body: { padding: 'p-3' }
        }">

            <CRow>
                <CCol>Cryptocurrencies</CCol>
                <CCol>
                    <div class="flex justify-end px-3 py-3.5 border-t border-gray-200 dark:border-gray-700">
                        <UPagination class="paginate-button" :ui="{ color: Pinkish }" v-model="page"
                            :page-count="listPerPage" :total="data.length"
                            :prev-button="{ icon: 'i-material-symbols:arrow-back-ios-rounded', class: 'paginate-button' }"
                            :next-button="{ icon: 'i-material-symbols:arrow-forward-ios-rounded' }" />
                    </div>
                </CCol>
                <!-- <UButton icon='i-material-symbols:arrow-back-ios-rounded' :style="{ color: Pinkish } color: pink></UButton>
                <UButton icon='i-material-symbols:arrow-forward-ios-rounded' class="paginate-button"></UButton> -->
            </CRow>
            <UTable :rows="slicedList" />
        </UCard>
    </CContainer>
</template>

<style scoped>
.paginate-button {
    color: #ff0080;
    border: 1px solid #ff0080;
    background-color: rgba(201, 76, 76, 0.1);
    /* border-radius: 0rem; */
    overflow: hidden;
    /* justify-content: center;
    align-items: center; */
    /* display: flex; */
}

th span {
    color: black;
}
</style>