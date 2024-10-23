<script stup>
import '@coreui/coreui/dist/css/coreui.min.css'
import 'bootstrap/dist/css/bootstrap.min.css'

</script>

<template>
    <CContainer style="overflow-y: hidden; height: 100vh">
        <CRow class="d-flex">
            <CCol style="max-width: 15.625rem;">
                <VerticalNavigationBar />
            </CCol>
            <CCol style="flex-grow: 10;">
                <HorizontalTopBar />
                <div>
                    <slot />
                </div>
                <CRow>
                    Copyright © 2022 Komgrip Technologies Co., Ltd.
                </CRow>
            </CCol>
        </CRow>
    </CContainer>
</template>


