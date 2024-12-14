<template>
    <div>
        <div class="container-fluid text-dark">
            <div class="row py-5" v-observe>
                <div class="col-12 col-md-6 d-flex justify-content-center align-items-center">
                    <div class="" style="width:1000px; max-width:70%">
                        <img src="/img/qr.png" class="w-100">
                    </div>
                </div>
                <div
                    class="col-12 col-md-6 d-flex flex-column justify-content-center align-items-md-start align-items-center">
                    <div class="text-md-start text-center mt-5 mt-md-0">
                        <p class="fs-1 fw-bold m-0 text-uppercase">CEQR Features</p>
                    </div>
                    <h3 class="mt-3 text-md-start text-center text-capitalize">Empower Your Business with Cutting-Edge
                        CEQR Features</h3>
                    <small class="text-md-start text-center">Explore tools designed to simplify operations, attract
                        customers, and maximize your business potential.</small>
                    <div class="mt-3 text-center text-md-start">
                        <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Generate and scan QR codes
                            effortlessly.</p>
                        <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Offer personalized coupon
                            codes for customer retention.</p>
                        <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Seamlessly manage orders
                            and product exchanges.</p>
                        <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Redeem rewards using QR
                            codes instantly.</p>
                        <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Create memorable gifting
                            experiences for your customers.</p>
                    </div>
                    <RouterLink to="">
                        <div class="btn btn-danger my-4 fs-5 fw-bold  text-capitalize" data-bs-toggle="modal"
                            data-bs-target="#queryModal">
                            Get started
                        </div>
                    </RouterLink>
                    <a href="#second" class><i class="bi bi-chevron-down fs-1 slide text-danger" ></i></a>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'BannerComp',
}
</script>
<style lang="">

</style>
