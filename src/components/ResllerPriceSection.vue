<template>
    <div class="my-3 py-3">
        <div class="my-3">
            <ul class="nav nav-pills justify-content-center" id="pills-tab" role="tablist">
                <div class="d-flex border  border-secondary p-2 px-3 rounded shadow">
                    <li class="nav-item" role="presentation" v-for="(price, index) in pricing" :key="price.id">
                        <button class="nav-link text-white" :class="{ 'active': index === 0 }" :id="'tab-' + index"
                            data-bs-toggle="pill" :data-bs-target="'#content-' + index" type="button" role="tab"
                            :aria-controls="'content-' + index" :aria-selected="index === 0">{{ price.name }}</button>
                    </li>
                </div>
            </ul>
            <div class="tab-content mt-2 pt-4" id="pills-tabContent">
                <div class="tab-pane fade" :class="{ 'show active': index === 0 }" v-for="(price, index) in pricing"
                    :key="price.id" :id="'content-' + index" role="tabpanel" :aria-labelledby="'tab-' + index"
                    tabindex="0">
                    <div class="table-responsive pb-4">
                        <table class="table table-bordered table-dark table-striped" style="width: 100%;">
                            <thead class="border-bottom  border-secondary">
                                <tr>
                                    <th class="text-start">Plan Features</th>
                                    <th scope="col" class="border-end text-center" v-for="plan in price.plans"
                                        :key="plan.id">
                                        <p class="mb-0">{{ plan.name }}</p>
                                        <p v-if="plan.price" class="mb-0">
                                            <small class="smaller">{{ plan.price }}</small>
                                        </p>
                                        <p v-else class="mb-0">
                                            <small class="smaller">Custom</small>
                                        </p>
                                        <p v-if="plan.price" class="mb-0">
                                            <small class="fw-light text-dark smaller">
                                                ₹ / year
                                            </small>
                                        </p>
                                        <p v-else class="mb-0">
                                            <small class="fw-light text-dark smaller">Contact</small>
                                        </p>
                                    </th>
                                </tr>
                            </thead>
                            <tbody class="border-start border-end  border-secondary">
                                <tr class="border-bottom  border-secondary" v-for="(feature, index) in price.plans[0].features"
                                    :key="index">
                                    <th class="pb-1 text-start">
                                        <span class="fw-normal smaller">{{ feature.name }}</span>
                                    </th>
                                    <td class="pb-1 text-center" v-for="plan in price.plans" :key="plan.id">
                                        <i v-if="plan.features[index].included"
                                            class="bi bi-check2 fs-5 text-warning smaller"></i>
                                        <i v-else class="bi bi-dash fs-5 text-secondary"></i>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "PriceSection",
    data() {
        return {
            pricing: [
                {
                    "id": "1",
                    "name": "Vendor",
                    "description": "Digital Marketing encompasses a range of online strategies and techniques to promote businesses, products, or services. It includes various specialized areas to help companies reach their target audience effectively in the digital space.",
                    plans: [
                        {
                            id: 1,
                            title: "Trial",
                            description: "Info Website",
                            price: '6,000',
                            mrp: '10,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: false },
                                { id: 6, name: "Rewards", included: false },
                                { id: 7, name: "Memberships", included: false },
                                { id: 7, name: "Certificates", included: false },
                                { id: 7, name: "Verifications", included: false },
                                { id: 7, name: "PR Management", included: false },
                                { id: 8, name: "Covisor Biz Badges", included: false },
                                { id: 3, name: "Covisor Biz Listing", included: false },
                                { id: 4, name: "Covisor Biz Marketing", included: false },
                                { id: 11, name: "Business Accounts", included: false },
                                { id: 12, name: "Reseller Accounts", included: false },
                            ],
                            
                        },
                        {
                            id: 2,
                            title: "Plus",
                            description: "Business Website",
                            price: '84,000',
                            mrp: '30,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: true },
                                { id: 6, name: "Rewards", included: true },
                                { id: 7, name: "Memberships", included: true },
                                { id: 7, name: "Certificates", included: true },
                                { id: 7, name: "Verifications", included: false },
                                { id: 7, name: "PR Management", included: false },
                                { id: 8, name: "Covisor Biz Badges", included: false },
                                { id: 3, name: "Covisor Biz Listing", included: false },
                                { id: 4, name: "Covisor Biz Marketing", included: false },
                                { id: 11, name: "Business Accounts", included: false },
                                { id: 12, name: "Reseller Accounts", included: false },
                            ],
                        },
                        {
                            id: 3,
                            title: "Elite",
                            description: "Catalog Website",
                            price: '3,00,000',
                            mrp: '60,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: true },
                                { id: 6, name: "Rewards", included: true },
                                { id: 7, name: "Memberships", included: true },
                                { id: 7, name: "Certificates", included: true },
                                { id: 7, name: "Verifications", included: true },
                                { id: 7, name: "PR Management", included: true },
                                { id: 8, name: "Covisor Biz Badges", included: true },
                                { id: 3, name: "Covisor Biz Listing", included: true },
                                { id: 4, name: "Covisor Biz Marketing", included: true },
                                { id: 11, name: "Business Accounts", included: true },
                                { id: 12, name: "Reseller Accounts", included: false },
                            ],
                        },
                        {
                            id: 4,
                            title: "Pro",
                            description: "Catalog Website",
                            // price: '29,999',
                            // mrp: '60,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: true },
                                { id: 6, name: "Rewards", included: true },
                                { id: 7, name: "Memberships", included: true },
                                { id: 7, name: "Certificates", included: true },
                                { id: 7, name: "Verifications", included: true },
                                { id: 7, name: "PR Management", included: true },
                                { id: 8, name: "Covisor Biz Badges", included: true },
                                { id: 3, name: "Covisor Biz Listing", included: true },
                                { id: 4, name: "Covisor Biz Marketing", included: true },
                                { id: 11, name: "Business Accounts", included: true },
                                { id: 12, name: "Reseller Accounts", included: true },
                            ],
                        },
                    ],
                },
                {
                    "id": "2",
                    "name": "Partner",
                    "description": "Website development involves creating and maintaining websites. It includes aspects such as web design, web publishing, web programming, and database management.",
                    plans: [
                        {
                            id: 1,
                            title: "Trial",
                            description: "Info Website",
                            price: '6,000',
                            mrp: '10,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: false },
                                { id: 6, name: "Rewards", included: false },
                                { id: 7, name: "Memberships", included: false },
                                { id: 7, name: "Certificates", included: false },
                                { id: 7, name: "Verifications", included: false },
                                { id: 7, name: "PR Management", included: false },
                                { id: 8, name: "Covisor Biz Badges", included: false },
                                { id: 3, name: "Covisor Biz Listing", included: false },
                                { id: 4, name: "Covisor Biz Marketing", included: false },
                                { id: 11, name: "Business Accounts", included: false },
                                { id: 12, name: "Reseller Accounts", included: false },
                            ],
                        },
                        {
                            id: 2,
                            title: "Plus",
                            description: "Business Website",
                            price: '84,000',
                            mrp: '30,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: true },
                                { id: 6, name: "Rewards", included: true },
                                { id: 7, name: "Memberships", included: true },
                                { id: 7, name: "Certificates", included: true },
                                { id: 7, name: "Verifications", included: false },
                                { id: 7, name: "PR Management", included: false },
                                { id: 8, name: "Covisor Biz Badges", included: false },
                                { id: 3, name: "Covisor Biz Listing", included: false },
                                { id: 4, name: "Covisor Biz Marketing", included: false },
                                { id: 11, name: "Business Accounts", included: false },
                                { id: 12, name: "Reseller Accounts", included: false },
                            ],
                        },
                        {
                            id: 3,
                            title: "Elite",
                            description: "Catalog Website",
                            price: '3,00,000',
                            mrp: '60,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: true },
                                { id: 6, name: "Rewards", included: true },
                                { id: 7, name: "Memberships", included: true },
                                { id: 7, name: "Certificates", included: true },
                                { id: 7, name: "Verifications", included: true },
                                { id: 7, name: "PR Management", included: true },
                                { id: 8, name: "Covisor Biz Badges", included: true },
                                { id: 3, name: "Covisor Biz Listing", included: true },
                                { id: 4, name: "Covisor Biz Marketing", included: true },
                                { id: 11, name: "Business Accounts", included: true },
                                { id: 12, name: "Reseller Accounts", included: false },
                            ],
                        },
                        {
                            id: 4,
                            title: "Pro",
                            description: "Catalog Website",
                            // price: '29,999',
                            // mrp: '60,000',
                            features: [
                                { id: 10, name: "Authorized Seller", included: true },
                                { id: 1, name: "Premium Accounts", included: true },
                                { id: 2, name: "Covisor Biz Course", included: true },
                                { id: 9, name: "Lead Management", included: true },
                                { id: 5, name: "Awards", included: true },
                                { id: 6, name: "Rewards", included: true },
                                { id: 7, name: "Memberships", included: true },
                                { id: 7, name: "Certificates", included: true },
                                { id: 7, name: "Verifications", included: true },
                                { id: 7, name: "PR Management", included: true },
                                { id: 8, name: "Covisor Biz Badges", included: true },
                                { id: 3, name: "Covisor Biz Listing", included: true },
                                { id: 4, name: "Covisor Biz Marketing", included: true },
                                { id: 11, name: "Business Accounts", included: true },
                                { id: 12, name: "Reseller Accounts", included: true },
                            ],
                        },
                    ],
                },
            ],
        }
    },
};
</script>
<style scoped>
.nav-link {
    transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-link.active {
    background-color: var(--brand-color) !important;
    color: black !important;
    transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
    /* transform: scale(1.2); */
}
</style>
