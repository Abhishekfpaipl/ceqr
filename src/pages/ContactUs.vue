<template>
    <div class="top-padding" >
        <TopSectionBanner />
        <div class="container " v-observe>
            <div class="row p-md-5 p-3 gx-5 text-dark align-items-center">
                <div class="col-12 col-md-6 pt-4 text-center">
                    <ContactForm />
                </div>
                <div class="col-12 col-md-6 mt-5 mt-md-0 pt-4 text-center">
                    <h3 class="text-uppercase cutout my-3"><span>Empower Your Brand with CEQR</span></h3>
                    <p class="text-capitalize fw-bold">"Leverage CEQR's advanced features <br> to boost your brand
                        visibility and connect like never before!"</p>
                    <ul class="text-start fw-bold mt-4">
                        <li class="mb-2">Create and share dynamic digital QR codes to showcase your products and
                            services.</li>
                        <li class="mb-2">Enhance customer engagement with interactive coupon codes and gift options.
                        </li>
                        <li class="mb-2">Streamline transactions and orders with scan-and-redeem QR solutions.</li>
                        <li class="mb-2">Unlock exclusive analytics to track your QR code interactions and growth
                            metrics.</li>
                        <li class="mb-2">Stand out with personalized QR codes designed for your brand’s identity.</li>
                    </ul>
                </div>


            </div>
        </div>
        <div class="container-fluid mt-5 py-5 text-dark" v-observe>
            <h1 class="text-uppercase mb-4 text-center">Need to get in touch with us?</h1>
            <div class="row">
                <div class="col-12 col-md-6 d-flex align-items-center justify-content-center">
                    <img src="/img/contactus.svg" style="width: 500px; max-width: 80%;" alt="">
                </div>
                <div class="col-12 col-md-6 mt-5 mt-md-0 d-flex">
                    <div class="row row-cols-1">
                        <div v-for="(icon, index) in contact" :key="index" class="col py-2"
                            @click="handleIconClick(icon.action)">
                            <div class="d-flex justify-content-between align-items-center border p-2 px-4">
                                <a class="text-dark d-flex gap-2 align-items-center text-decoration-none"
                                    :href="icon.url" target="_blank">
                                    <i :class="icon.icon" class=""></i>
                                    <p class="text-start ms-2 fw-bold mb-0">{{ icon.name }}</p>
                                </a>
                                <img src="/img/right-arrow.svg" style="width: 30px;filter: invert(1);" alt="">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import TopSectionBanner from "@/components/TopSectionBanner.vue";
import ContactForm from "@/components/ContactForm.vue";
export default {
    name: "ContactPage",
    components: {
        TopSectionBanner,
        ContactForm,
    },
    data() {
        return {
            contact: [
                { name: 'support@ceqr.com', icon: 'bi-envelope fs-3', color: 'red', action: 'openEmail' },
                { name: '8802172121', icon: 'bi-telephone-fill fs-3', color: 'black', action: 'openDialer' },
                { name: '8802172121', icon: 'bi-whatsapp fs-3', color: 'green', action: 'openWhatsapp' },
                { name: 'B1/632, Janakpuri, Delhi', icon: 'bi-geo-fill fs-3', color: 'black', action: 'openMaps' },
            ],
            folows: [
                {
                    icon: 'bi bi-facebook fs-3',
                    name: 'Facebook',
                    color: 'blue',
                    url: 'https://www.facebook.com/yourpage'
                },
                {
                    icon: 'bi bi-twitter-x fs-3',
                    name: 'Twitter',
                    color: 'black',
                    url: 'https://www.instagram.com/yourprofile'
                },
                {
                    icon: 'bi bi-youtube fs-3',
                    name: 'YouTube',
                    color: 'red',
                    url: 'https://www.youtube.com/'
                },
                {
                    icon: 'bi bi-linkedin fs-3',
                    name: 'LinkedIn',
                    color: 'blue',
                    url: 'https://www.linkedin.com/in/yourprofile'
                },
            ],
            mobile: '',
            email: '',
            number: '',
            note: '',
        }
    },
    methods: {
        loginAccount() {
            console.log(this.mobile, this.email, this.number, this.note)
        },
        submitQuery() {
            if (this.name != '' && this.note != '') {
                const phoneNumber = '918802172121'; // Replace with your WhatsApp number
                const message = `Hello, my name is ${this.name} i would like to book my 30 mins free consultation. Here are some additional notes: ${this.note}.`;
                const whatsappUrl = `https://api.whatsapp.com/send?phone=${phoneNumber}&text=${encodeURIComponent(message)}`;
                window.open(whatsappUrl, '_blank');
                this.name = "";
                this.note = "";
            }
        },
        handleIconClick(action) {
            const phoneNumber = '+918802172121';
            const emailAddress = 'support@covisor.in';
            const location = '2nd Floor, Block B1/632, Janakpuri, Delhi, 110058';

            switch (action) {
                case 'openEmail':
                    window.location.href = `mailto:${emailAddress}`;
                    break;
                case 'openDialer':
                    window.location.href = `tel:${phoneNumber}`;
                    break;
                case 'openWhatsapp':
                    window.open(`https://wa.me/${phoneNumber}?text=Hello...`, '_blank');
                    break;
                case 'openMaps':
                    window.open(`https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(location)}`, '_blank');
                    break;
                default:
                    break;
            }
        },
    }
}
</script>

<style scoped>
.cutout {
    overflow: hidden;
    text-align: center;
}

.cutout span {
    background: linear-gradient(90deg, rgba(254, 242, 159, 1) 0%, rgba(210, 163, 73, 1) 50%, rgba(254, 242, 159, 1) 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
}

.cutout>span {
    position: relative;
    display: inline-block;
}

.cutout>span:before,
.cutout>span:after {
    content: "";
    position: absolute;
    top: 50%;
    width: 900px;
    /* Adjust width as needed */
    margin: 0 20px;
}

.cutout>span:before {
    right: 100%;
    border-bottom: 2px solid;
    border-color: var(--brand-color);
    border-image-slice: 1;
}

.cutout>span:after {
    left: 100%;
    border-bottom: 2px solid;
    border-color: var(--brand-color);
    border-image-slice: 1;
}
</style>
