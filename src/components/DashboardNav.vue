<template>
    <div class="position-fixed w-100" style="z-index: 10;">
        <div class="containerr d-flex justify-content-between align-items-center" ref="topnav">
            <div class="w-100 d-flex align-items-center justify-content-between gap-3">
                <router-link to="/" class="text-decoration-none text-dark d-flex align-items-center">
                    <img :src="`${publicPath}${img}`" style="width: 40px; object-fit: contain;">
                    <div class="d-flex flex-column align-items-start ">
                        <span class="text-uppercase fw-bold fs-4 lh-1 ms-2">ceqr</span>
                    </div>
                </router-link>
                <div class="d-flex align-items-center gap-2 slide" data-bs-toggle="modal" data-bs-target="#queryModal">
                    <i class="bi bi-headset fs-3 method1 "></i>
                    <p class="text-white mb-1 d-md-block d-none">Contact</p>
                </div>
            </div>
        </div>
    </div>

    <BottomShareIcons />
</template>

<script>
import BottomShareIcons from "@/components/BottomShareIcons.vue";
export default {
    name: 'ProductTopnav',
    components: {
        BottomShareIcons,
    },
    data() {
        return {
            publicPath: process.env.BASE_URL,
            img: "img/logo.png",
            backgroundOpacity: 0,
            hideOnScroll: true,
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            const scrollPercentage = (scrollTop / (document.documentElement.scrollHeight - window.innerHeight)) * 100;
            // console.log(scrollTop)
            // console.log(scrollPercentage)
            if (scrollPercentage >= 5 && scrollPercentage <= 6) {
                this.backgroundOpacity = 0.5;
                this.hideOnScroll = true;
            } else if (scrollPercentage > 5) {
                this.backgroundOpacity = 1;
                this.hideOnScroll = false;
            } else {
                this.backgroundOpacity = 0;
                this.hideOnScroll = true;
            }
        },
    }
};
</script>

<style scoped>
.hide-on-scroll {
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
}

.containerr { 
    background: var(--bg-primary);
    padding: 1rem;
} 
</style>