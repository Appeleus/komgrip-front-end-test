<script setup>
import '@coreui/coreui/dist/css/coreui.min.css'
import 'bootstrap/dist/css/bootstrap.min.css'
</script>

<template>
    <UBreadcrumb :ui="{ color: 'red', }" 
    divider="/" :links="[
        { label: 'Pages', to: '/' },
        { label: 'Dashboard' }
    ]" />
</template>

<style scoped></style>