<script setup>
const props = defineProps({
    currentPage: String
})

</script>

<template>
    <CRow class="d-flex">
        <CCol>
            <BreadCrumb />
            <h2>{{props.currentPage}}</h2>
        </CCol>
        <CCol>
            <UIcon name="i-ic:sharp-person-2" />
        </CCol>
    </CRow>
</template>

<style></style>