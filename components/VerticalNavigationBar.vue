<script setup>
import '@coreui/coreui/dist/css/coreui.min.css'
import 'bootstrap/dist/css/bootstrap.min.css'
import { ref, watch } from 'vue'

const currentPage = ref('dashboard')
function setCurrentPage(newPage) {
    currentPage.value = newPage;

    watch(currentPage.value, (newValue) => {
        console.log(`Current page changed to: ${newValue}`);
    });
}

</script>

<template>
    <CContainer class="d-flex" style="max-height:80px; padding: 24px 32px">
        <CRow class="d-flex">
            <img src="../assets/img/logo.png" style="max-height: 100%" />
            <span class="ms-1 d-flex" style="font-weight: 500; align-items: center; justify-content: center;">Komgrip
                Technologies</span>
        </CRow>
    </CContainer>

    <UDivider class="px-3 mt-0" />

    <CContainer class="d-flex" style="margin: 32px;">
        <CRow>
            <nav>
                <ul style="width: 100%">
                    <li>
                        <NuxtLink to="/dashboard" @click="setCurrentPage('dashboard')">
                            <UBadge :class="currentPage == 'dashboard' ? 'badge-nav-selected' : 'badge-nav-unselected'">
                                <UIcon class="i-material-symbols:storefront-rounded"
                                    :style="{ width: '18px', height: '18px' }" />
                            </UBadge> Dashboard
                        </NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/menu1" @click="setCurrentPage('menu1')">
                            <UBadge :class="currentPage == 'menu1' ? 'badge-nav-selected' : 'badge-nav-unselected'">
                                <UIcon class="i-material-symbols:square-rounded"
                                    :style="{ width: '18px', height: '18px' }" />
                            </UBadge> Menu 1
                        </NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/menu2" @click="setCurrentPage('menu2')">
                            <UBadge :class="currentPage == 'menu2' ? 'badge-nav-selected' : 'badge-nav-unselected'">
                                <UIcon class="i-material-symbols:square-rounded"
                                    :style="{ width: '18px', height: '18px' }" />
                            </UBadge> Menu 2
                        </NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/menu3" @click="setCurrentPage('menu3')">
                            <UBadge :class="currentPage == 'menu3' ? 'badge-nav-selected' : 'badge-nav-unselected'">
                                <UIcon class="i-material-symbols:square-rounded"
                                    :style="{ width: '18px', height: '18px' }" />
                            </UBadge> Menu 3
                        </NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/menu4" @click="setCurrentPage('menu4')">
                            <UBadge :class="currentPage == 'menu4' ? 'badge-nav-selected' : 'badge-nav-unselected'">
                                <UIcon class="i-material-symbols:square-rounded"
                                    :style="{ width: '18px', height: '18px' }" />
                            </UBadge> Menu 4
                        </NuxtLink>
                    </li>
                </ul>
            </nav>
        </CRow>
    </CContainer>
    <HelpCard />
</template>

<style scoped>
CContainer {
    font-size: 14px;
    color: #344767;
}

ul li {
    padding: 10px 0px;
}

li a {
    font-size: 14px;
    color: #5e6c88;
    justify-content: center;
    align-items: center;
    text-decoration: none;
    white-space: nowrap;
    padding: 10px;
}

li a.router-link-active {
    width: 100%;
    background-color: white;
    box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
    font-weight: 500;
    color: #2b3f5f;
    border-radius: 5px;
}

.badge-nav-selected {
    background-image: linear-gradient(310deg, #cb0b9f, #cb0b9f);
    box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
    width: 32px;
    height: 32px;

}

.badge-nav-unselected {
    background-image: linear-gradient(310deg, #fff, #fff);
    box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
    width: 32px;
    height: 32px;
}

.badge-nav-selected span {
    color: white;
}

.badge-nav-unselected span {
    color: #344767;
}

ul {
    padding: 0px 0px;
}
</style>