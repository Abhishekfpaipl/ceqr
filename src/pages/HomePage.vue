<template>
    <div class="text-white top-padding">
        <TopBanner />
        <Banner brandColorOne="#125252" />
        <div class="my-5">
            <StepsForRegistration />
        </div> 
        <div class="my-5">
            <LeadManagement :values="leads" title="Our Features," subtitle=" " />
        </div>
        <div class="my-5">
            <WhyChooseUs :description="whychooseUs" title="why choose us" />
        </div> 
        <div class="my-5" id="second">
            <PriceSection />
        </div>
        <!-- <div class="my-5">
            <AutoScrolling v-observe />
        </div> -->
        <div class="">
            <CounterSection brandColorOne="#125252" brandTextColor="#78E6B7" name1="customers" :value1="50"
                name2="years" :value2="1" name3="team" :value3="150" v-observe />
        </div>
        <div class="py-5">
            <HomeTestimonialSection />
        </div>
    </div>
</template>

<script>
import TopBanner from "@/components/TopBanner.vue";
import Banner from "@/components/BannerSection.vue";
import LeadManagement from "@/components/LeadManagement.vue";
// import AutoScrolling from "@/components/AutoScrolling.vue"; 
// import PriceSection from "@/components/PriceSection.vue";
import StepsForRegistration from "@/components/StepsForRegistration.vue"; 
import CounterSection from "@/components/CounterSection.vue";
import WhyChooseUs from "@/components/WhyChooseUs.vue";
// import TempFaqs from "@/components/business-site/TempFaqs.vue"; 
export default {
    name: "ListYourBusiness",
    components: {
        TopBanner,
        Banner,
        LeadManagement,
        // AutoScrolling, 
        // PriceSection,
        StepsForRegistration, 
        CounterSection,
        WhyChooseUs,
        // TempFaqs,  
    },
    data() {
        return {
            faqs: [
                {
                    id: 1,
                    question: "What does a CRM system do ?",
                    answer: "At its core, the CRM system is designed to manage communications with customers and align all stakeholders involved in interactions with them. However, CRM systems have evolved to perform complex tasks like automating processes, setting up workflows, tracking all conversations and using all the sales and marketing data to derive meaningful reports."
                },
                {
                    id: 2,
                    question: "Why is CRM important for marketers?",
                    answer: "With CRM, marketers can check the performance of their marketing sources, evaluate touchpoints, and more. A CRM helps marketers better understand customers and tune their messaging accordingly. Marketers can also personalize their messages using lead details captured in the CRM platform."
                },
                {
                    id: 3,
                    question: "What is CRM software used for?",
                    answer: "Aligning teams and automating customer-facing processes. Standardizing sales processes and automating them. Managing customer tickets. Tracking the performance of various marketing sources. Reporting and analytics"
                },
                {
                    id: 4,
                    question: "Why is CRM important in sales?",
                    answer: "Because sales reps pursue many leads, CRM plays a significant role in organizing them as per their stages in the sales pipeline. It also helps them keep track of interactions with prospects, schedule meetings, set reminders, and more."
                },
                {
                    id: 5,
                    question: "How much does a CRM system cost?",
                    answer: "Depending on the features, the cost of a CRM system may start from $10-$25 per user per month. CRM companies also offer custom plans for specific features."
                },
            ],
            whychooseUs: [
                {
                    title: 'Ensure Zero Lead Leakage',
                    icon: 'bi-headset'
                },
                {
                    title: 'No Missing Follow - ups',
                    icon: 'bi-thumbs-up'
                },
                {
                    title: "Increase 80 % Additional Sales",
                    icon: 'bi-currency-ruppee'
                },
                {
                    title: "Cost effective",
                    icon: 'bi-journal'
                },
                {
                    title: "Secured Plateform",
                    icon: 'bi-stars'
                },
                {
                    title: "Free support",
                    icon: 'bi-stars'
                },
                {
                    title: "Modern Interface",
                    icon: 'bi-stars'
                },
                {
                    title: "Easy Setup & Fast Adoption",
                    icon: 'bi-stars'
                },
            ],
            leads: [
                {
                    id: 1,
                    icon: 'bi-box fs-4', // Suggested icon for Products
                    image: "/img/products.png", // Replace with the actual image path
                    title: "Products",
                    description: "Browse and explore our wide range of products available for purchase."
                },
                {
                    id: 2,
                    icon: 'bi-gift fs-4', // Suggested icon for Gift
                    image: "/img/gift.png", // Replace with the actual image path
                    title: "Gift",
                    description: "Send and receive amazing gifts, perfect for any occasion."
                },
                {
                    id: 3,
                    icon: 'bi-qr-code fs-4', // Suggested icon for QR Code
                    image: "/img/qr.png", // Replace with the actual image path
                    title: "QR Code",
                    description: "Generate and scan QR codes for quick and secure transactions."
                },
                {
                    id: 4,
                    icon: 'bi-ticket-perforated fs-4', // Suggested icon for Coupon Code
                    image: "/img/coupon.png", // Replace with the actual image path
                    title: "Coupon Code",
                    description: "Apply coupon codes to get exclusive discounts and offers."
                },
                {
                    id: 5,
                    icon: 'bi-cart fs-4', // Suggested icon for Order
                    image: "/img/order.png", // Replace with the actual image path
                    title: "Order",
                    description: "Place an order quickly and easily with a few clicks."
                },
                {
                    id: 6,
                    icon: 'bi-camera fs-4', // Suggested icon for Scan QR Code
                    image: "/img/qr.png", // Replace with the actual image path
                    title: "Scan QR Code",
                    description: "Use the scanner to quickly access information by scanning QR codes."
                },
                {
                    id: 7,
                    icon: 'bi-check-circle fs-4', // Suggested icon for Redeem QR Code
                    image: "/img/qr.png", // Replace with the actual image path
                    title: "Redeem QR Code",
                    description: "Redeem offers and rewards by scanning your QR code."
                },
                {
                    id: 8,
                    icon: 'bi-arrow-repeat fs-4', // Suggested icon for Exchange Gifts
                    image: "/img/gift.png", // Replace with the actual image path
                    title: "Exchange Gifts",
                    description: "Exchange gifts with friends and loved ones easily and conveniently."
                },
            ],
            customers: [
                {
                    id: 1,
                    show: false,
                    imgr: '/img/users/1.png',
                    name: 'Ram',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "We initially thought Saleswik was a small tool that only stores client data but once we started working on it, we knew its depth. We are very excited to use the new features like Team Pipelines, Email-in, and File Cabinet. We 100% recommend Saleswik to everyone!"
                },
                {
                    id: 2,
                    show: false,
                    imgr: '/img/users/2.png',
                    name: 'Shyam',
                    company: 'XYz Pvt Ltd',
                    rating: '4.5',
                    text: "Saleswik was the perfect solution for our startup, which was moving from paper-based and Excel sheets to an automated solution for sales outreach and managing incoming calls. It has all the basic functionality of other leading CRMs at half the price. In addition, onboarding/training was provided at no additional cost. I highly recommend Zoho Saleswik for any micro business."
                },
                {
                    id: 3,
                    show: false,
                    imgr: '/img/users/3.png',
                    name: 'Nikhil',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "Loved its UI. I have tried many other apps but this app is the best. The details in which the products are shown in picture is above all."
                },
                {
                    id: 4,
                    show: false,
                    imgr: '/img/users/4.png',
                    name: 'Abhishek',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "The general idea was to keep everything in one place and at an affordable price, and Saleswik was very accessible that way, and with the ability to expand without switching CRMs."
                },
                {
                    id: 5,
                    show: false,
                    imgr: '/img/users/5.png',
                    name: 'Rajan',
                    company: 'XYz Pvt Ltd',
                    rating: '4',
                    text: "When you work with software that is structured with features that make it so easy to use—that's when you realize you've struck gold and you don't want to go anywhere else. The pricing is also just right and ideal for small businesses."
                },
                {
                    id: 6,
                    show: false,
                    imgr: '/img/users/1.png',
                    name: 'Yogesh',
                    company: 'XYz Pvt Ltd',
                    rating: '4.5',
                    text: "Saleswik has been really helpful for us to keep a track on contacts and deals. Since we are small team, Saleswik was so user-friendly that we were able to start using from week 1 of our trial."
                },
                {
                    id: 7,
                    show: false,
                    imgr: '/img/users/2.png',
                    name: 'Lokesh',
                    company: 'XYz Pvt Ltd',
                    rating: '4',
                    text: "The CRM options available in the market are either too expensive, with complex features that are not essential for a small business, or are priced less with nominal features. But Saleswik is game-changing. It has exceeded our expectations such that V4 Creative cannot work without it."
                },
                {
                    id: 8,
                    show: false,
                    imgr: '/img/users/3.png',
                    name: 'Bhasker',
                    company: 'XYz Pvt Ltd',
                    rating: '3.5',
                    text: "As vendor and customers needed order visibility, we wanted to automate the entire business and found only Saleswik to be the best suited in terms of integration."
                },
                {
                    id: 9,
                    show: false,
                    imgr: '/img/users/4.png',
                    name: 'Vivek',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "Saleswik has stayed true to its value proposition—a CRM tailored for small businesses and startups."
                },
                {
                    id: 10,
                    show: false,
                    imgr: '/img/users/5.png',
                    name: 'Ankit',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "Since the implementation of Saleswik, we have seen positive outcomes in business operations and the accessibility of data. One glance at the Dashboards indicates the performance of my sales folks!"
                },
                {
                    id: 11,
                    show: false,
                    imgr: '/img/users/1.png',
                    name: 'Karan',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "The mobile app of Saleswik increases productivity on a whole different level. As a small business, it gives us the edge over our competitors and we're very happy to use Saleswik!"
                },
                {
                    id: 12,
                    show: false,
                    imgr: '/img/users/2.png',
                    name: 'Rajat',
                    company: 'XYz Pvt Ltd',
                    rating: '4',
                    text: "Saleswik helps me stay on track, lets me know where I am at any point of time and what I need to do to reach where I really want to go!"
                },
                {
                    id: 13,
                    show: false,
                    imgr: '/img/users/3.png',
                    name: 'Ajay',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "Since I started using Saleswik, no lead has been lost. The student conversion rate has increased by 25 percent, to 30 percent."
                },
                {
                    id: 14,
                    show: false,
                    imgr: '/img/users/4.png',
                    name: 'Vikas',
                    company: 'XYz Pvt Ltd',
                    rating: '5',
                    text: "Saleswik has helped us to decentralize information. Now all the team has access to the documents and sales information. We no longer have the problem that some documents is stored on the PC of a teammate who is not accessible at the time."
                },
            ]
        }
    },
}
</script>