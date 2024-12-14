<template>
    <div class="container-fluid text-dark bg-ligh py-5">
        <h1 class="text-center mb-2">Millions Globally Trust our QR Code Tech</h1>
        <p class="text-center text-muted small mb-4">Our QR Code solution is powering millions of QR Code Scans around the globe</p>
        <div class="row row-cols-1 row-cols-md-3 g-2">
            <div v-for="(item, index) in fav" :key="index" class="col" v-observe>
                <div class="p-2 card brand-bg text-white shadow">
                    <i v-if="item.icon" class="bi fs-3" :class="item.icon"></i>
                    <p class="fw-bold fs-1 mb-0 d-flex justify-content-center align-items-center"
                        style="color:var(--brand-color) !important;">
                        <AutoCounter :data="item.data" /><span>&nbsp;{{ item.info }}+</span>
                    </p>
                    <p class="small" style="color:var(--brand-color) !important;">{{ item.label }}</p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import AutoCounter from '@/components/AutoCounter.vue';
export default {
    components: {
        AutoCounter,
    },
    data() {
        return {
            fav: [
                {
                    data: 120,
                    info: 'M',
                    icon: "bi-qr-code",
                    label: 'QR Codes'
                },
                {
                    data: 150,
                    info: 'M',
                    icon: "bi-qr-code-scan",
                    label: 'Scans'
                },
                {
                    data: 800,
                    info: 'K',
                    icon: "bi-person",
                    label: 'Users'
                },
            ]

        }
    }
}
</script>
<style lang="">

</style>